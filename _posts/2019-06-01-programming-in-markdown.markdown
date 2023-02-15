---
layout: post
title: "Programming in Markdown"
categories: programming, markdown
---
Markdown is a lightweight markup language that is used to format text in a simple and consistent way. It was first created in 2004 by John Gruber and Aaron Swartz as a way to write content for the web that was easy to read and write.

Markdown is designed to be easy to learn and use. It uses simple syntax to format text, making it easy to create headings, lists, links, and other formatting elements. Markdown can be used in a wide variety of contexts, including writing blog posts, creating documentation, and writing code comments.

One of the key features of Markdown is its simplicity. Markdown uses plain text that can be easily read and edited using any text editor. This makes it easy to collaborate on documents and to transfer files between different devices and platforms. Additionally, Markdown is supported by a wide variety of software tools and platforms, including blogging platforms, content management systems, and online forums.

Another important feature of Markdown is its flexibility. Markdown can be customized and extended to support a wide variety of use cases. For example, Markdown supports the creation of tables, code blocks, and mathematical equations. Additionally, there are many third-party tools and libraries that extend the functionality of Markdown, such as Pandoc, which can convert Markdown to other formats like HTML, LaTeX, and PDF.

Markdown is also popular among programmers, as it can be used to create code blocks and inline code snippets. This is particularly useful for writing documentation and sharing code examples. Many code editors also support Markdown, allowing programmers to write and preview Markdown documents without leaving their development environment.

Following table provides a quick overview of frequently used Markdown syntax elements. It does not cover every case, so if you need more information about any of these elements, refer to the reference guides for [basic syntax](https://www.markdownguide.org/basic-syntax) and [extended syntax](https://www.markdownguide.org/extended-syntax).

| Element | Markdown Syntax |
| - | - |
| Heading | \# for H1, \#\# for H2 and so on |
| Bold | \*\*bold text\*\* | 
| Italic | \*italicized text\* |
| Blockquote | \> blockquote | 
| Ordered List | Just add 1., 2. and so on in front of list elements |
| Unordered List | Just add a \- or \* in front of list elements | 
| Code | \`code` |
| Horizontal Rule | three or more \*, \-, or \_ | 
| Link | \[title]\(https://www.example.com) |
| Image | \!\[alt text]\(file-path/image.jpg)\{:class="img-responsive"} | 

Now that we have reviewed some of the basic syntax elements, lets familiarize ourself with some advance syntax elements.

| Element | Markdown Syntax |
| - | - |
| Table | \| for vertical lines and - for horizontal lines |
| Code Block | \`\`\` code \`\`\` | 
| Footnote |  [^1]: This is the footnote. |
| Heading ID | \#\#\# Heading \{\#custom-id} | 
| Strikethrough | \~\~The world is flat.\~\~ |
| URL | <https://www.markdownguide.org> |
| Email | <fake@example.com> |
| Escape character | \\ |

Markdown also offers syntax highlighting for various programming languages when we specify a code block. Most of the time all we need to do is just mention the name of the programming language after the opening \`\`\`, like \`\`\`python. Following is a curated list of supported programming languages:

| Language | Supported file types |
| - | - |
| bash | '\*.sh', '\*.ksh', '\*.bash', '\*.ebuild', '\*.eclass' |
| bat | '\*.bat', '\*.cmd' |
| c | '\*.c', '\*.h' |
| cpp | '\*.cpp', '\*.hpp', '\*.c++', '\*.h++', '\*.cc', '\*.hh', '\*.cxx', '\*.hxx', '\*.pde' |
| csharp | '\*.cs' |
| css | '\*.css' |
| fortran | '\*.f', '\*.f90' |
| go | '\*.go' |
| html | '\*.html', '\*.htm', '\*.xhtml', '\*.xslt' |
| java | '\*.java' |
| js | '\*.js' |
| markdown | '\*.md' |
| perl | '\*.pl', '\*.pm' |
| php | '\*.php', '\*.php(345)' |
| postscript | '\*.ps', '\*.eps' |
| python | '\*.py', '\*.pyw', '\*.sc', 'SConstruct', 'SConscript', '\*.tac' |
| rb or ruby | '\*.rb', '\*.rbw', 'Rakefile', '\*.rake', '\*.gemspec', '\*.rbx', '\*.duby' |
| sql | '\*.sql' |
| vbnet | '\*.vb', '\*.bas' |
| xml | '\*.xml', '\*.xsl', '\*.rss', '\*.xslt', '\*.xsd', '\*.wsdl' |
| yaml | '\*.yaml', '\*.yml' |



# A great heading (h1)
## Another great heading (h2)
### Some great subheading (h3)
#### You might want a sub-subheading (h4)
##### Could be a smaller sub-heading, `pacman` (h5)
###### Small yet significant sub-heading  (h6)


### Code box

```html
<html>
  <head>
  </head>
  <body>
    <p>Hello, World!</p>
  </body>
</html>
```


### List

- First item, yo
- Second item, dawg
- Third item, what what?!
- Fourth item, fo sheezy my neezy


### Numbered list

1. First item, yo
2. Second item, dawg
3. Third item, what what?!
4. Fourth item, fo sheezy my neezy

### Comments

{% comment %}
Might you have an include in your theme? Why not try it here!
{% include my-themes-great-include.html %}
{% endcomment %}


### Tables

Title 1               | Title 2               | Title 3               | Title 4
--------------------- | --------------------- | --------------------- | ---------------------
lorem                 | lorem ipsum           | lorem ipsum dolor     | lorem ipsum dolor sit
lorem ipsum dolor sit | lorem ipsum dolor sit | lorem ipsum dolor sit | lorem ipsum dolor sit
lorem ipsum dolor sit | lorem ipsum dolor sit | lorem ipsum dolor sit | lorem ipsum dolor sit
lorem ipsum dolor sit | lorem ipsum dolor sit | lorem ipsum dolor sit | lorem ipsum dolor sit


Title 1 | Title 2 | Title 3 | Title 4
--- | --- | --- | ---
lorem | lorem ipsum | lorem ipsum dolor | lorem ipsum dolor sit
lorem ipsum dolor sit amet | lorem ipsum dolor sit amet consectetur | lorem ipsum dolor sit amet | lorem ipsum dolor sit
lorem ipsum dolor | lorem ipsum | lorem | lorem ipsum
lorem ipsum dolor | lorem ipsum dolor sit | lorem ipsum dolor sit amet | lorem ipsum dolor sit amet consectetur

In summary, Markdown is a simple and flexible markup language that is widely used for formatting text on the web. Its simplicity and ease of use make it an attractive option for writing and sharing documents, and its flexibility allows it to be customized and extended to support a wide variety of use cases. Whether writing blog posts, creating documentation, or sharing code examples, Markdown is a valuable tool for anyone who wants to format text in a consistent and easy-to-read way.

For a more complete list consider visiting [Codebase](https://support.codebasehq.com/articles/tips-tricks/syntax-highlighting-in-markdown).

By the way this page was written using markdown and rendered to HTML using Jekyll. 

Comments welcome!

{% include disqus_comments.html %}
