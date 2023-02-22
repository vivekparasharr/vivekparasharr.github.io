---
layout: post
title: "Make Your Own Python Package and Share with Others in AWS SageMaker"
categories: programming, cloud, python, pyspark, aws
permalink: /programming/python/package-functions
---
Packaging in Python is the process of creating distributable packages of code that can be easily installed and used by other developers. These packages can contain modules, functions, classes, and other components that can be shared and reused across different projects.

#### Advantages of packaging functions
- Modularity: By packaging related functions together, you can organize your code into reusable modules that can be used across multiple projects. This can help to avoid duplicating code and makes it easier to maintain and update your code.
- Encapsulation: Packaging functions in a module can help to encapsulate the implementation details of the functions, making it easier to use them without worrying about the underlying implementation.
- Code reusability: If you have a set of functions that perform a specific task, packaging them into a module can make it easy to reuse those functions in other projects without having to rewrite them.
- Code organization: Packaging functions into a module can help to keep your code organized and easy to navigate. This can be especially helpful for larger projects with many different functions.
- Easy installation: By packaging functions into a module, you can make it easy for others to install and use your code by simply installing the module using pip. This can make it easier to share your code with others and collaborate on projects.

---

#### Process of creating a package
Here's an example of a Python package with functions to add and subtract two numbers and how to make it available in Amazon SageMaker

##### Create package directory
First, create a new directory for your package and navigate to it in your terminal or command prompt.
Then, Create a new file called __init__.py in your package directory. This file is required to make your directory a Python package.
Then, create a new file called vp_math.py in your package directory. This file will contain the functions to add and subtract two numbers. Your directory structure should look something like this:
```lua
vp_package/
    __init__.py
    vp_math.py
```

##### Adding code
Now you can add the following code to your vp_math.py file:
```python
def add(x, y):
    return x + y

def subtract(x, y):
    return x - y
```

##### Create a setup.py file
Now, create a setup.py file in your package directory, with the following code:
```python
from setuptools import setup

setup(
    name='vp_package',
    version='0.0.1',
    description='A basic package with functions to add and subtract two numbers',
    packages=['vp_package']
)
```

---

##### Build and package
Now, build and package the distribution file by running the following command in your terminal or command prompt in your package directory:
```bash
python setup.py sdist
```
This will create a .tar.gz file in a newly created dist directory.

---

##### Upload the package to a shared place
Upload the package to a S3 bucket that SageMaker can access. For this, you can use the AWS CLI, for example:
```bash
aws s3 cp dist/vp_package-0.0.1.tar.gz s3://my-bucket/
```
Make sure to replace my-bucket with the name of the S3 bucket you want to use.

---

#### How to use the package
In SageMaker, create a new Jupyter Notebook and include the following code:
```python
!pip install vp_package==0.0.1 --target /home/ec2-user/SageMaker/vp_package

from vp_package.vp_math import add, subtract

print(add(2, 3)) # Output: 5
print(subtract(5, 2)) # Output: 3
```
The !pip install command installs your package into the SageMaker notebook instance. The --target argument tells pip where to install the package, in this case, in the /home/ec2-user/SageMaker/vp_package directory.

This should import the functions from your package and allow you to use them in SageMaker.

Note that in a production environment, you would want to host your package on a PyPI server or a private package repository instead of manually uploading it to S3.

Comments welcome!

{% include disqus_comments.html %}
