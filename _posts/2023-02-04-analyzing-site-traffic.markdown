---
layout: post
title: "Analyzing Website Traffic Using Google Analytics and AWS"
categories: web analytics, website analytics, google analytics, aws, ec2, python, plotly
---
To analyze website traffic using Google Analytics and AWS, you can follow these high-level steps:

- Set up a Google Analytics account and obtain the tracking code for your website.
- Set up an S3 bucket in AWS to store the data from Google Analytics.
- Set up an AWS Lambda function to pull data from the Google Analytics API and store it in the S3 bucket.
- Set up an AWS Glue crawler to crawl the S3 bucket and create a data catalog in the AWS Glue Data Catalog.
- Set up an Amazon Athena query to analyze the data in the S3 bucket using SQL-like queries.

---

Here's some sample code to get started:

##### Importing Required Packages
```python
import boto3
import datetime
from google.oauth2 import service_account
from googleapiclient.discovery import build
from googleapiclient.errors import HttpError
```

##### Set up the Google Analytics API credentials
```python
credentials = service_account.Credentials.from_service_account_file('/path/to/credentials.json')
```

##### Set up the S3 bucket
```python
s3 = boto3.client('s3')
bucket_name = 'my-bucket-name'
```

##### Set up the Lambda function to pull data from the Google Analytics API and store it in the S3 bucket
```python
def lambda_handler(event, context):
    try:
        service = build('analyticsreporting', 'v4', credentials=credentials)

        # Query the Google Analytics API for website traffic data
        response = service.reports().batchGet(
            body={
                'reportRequests': [
                    {
                        'viewId': '12345678',
                        'dateRanges': [{'startDate': '7daysAgo', 'endDate': 'today'}],
                        'metrics': [{'expression': 'ga:sessions'}],
                        'dimensions': [{'name': 'ga:date'}, {'name': 'ga:hour'}]
                    }
                ]
            }
        ).execute()

        # Store the website traffic data in the S3 bucket
        now = datetime.datetime.now().strftime('%Y-%m-%d-%H-%M-%S')
        filename = f'{now}-website-traffic.csv'
        data = response['reports'][0]['data']['rows']
        s3.put_object(Body=str(data), Bucket=bucket_name, Key=filename)

    except HttpError as error:
        print(f'An error occurred: {error}')
        data = None
```

##### Set up the Glue crawler to crawl the S3 bucket and create a data catalog
```python
glue = boto3.client('glue')

response = glue.create_crawler(
    Name='my-crawler',
    Role='my-glue-role',
    DatabaseName='my-database',
    Targets={
        'S3Targets': [
            {
                'Path': f's3://{bucket_name}/'
            }
        ]
    }
)
```

##### Set up the Athena query to analyze the website traffic data in the S3 bucket
```python
athena = boto3.client('athena')

response = athena.start_query_execution(
    QueryString='SELECT * FROM my_database.my_table WHERE sessions > 100',
    QueryExecutionContext={
        'Database': 'my_database'
    },
    ResultConfiguration={
        'OutputLocation': f's3://{bucket_name}/query_results/'
    }
)
```

Note that this is just a sample code to get started, and you will need to customize it to match your specific use case. Also note that there will be additional configuration and setup required, such as setting up the IAM roles and permissions for the Lambda function, Glue crawler, and Athena query, and configuring the Google Analytics API to allow access to your website data.

Comments welcome!

{% include disqus_comments.html %}
