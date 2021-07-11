---
layout: post
title:  "[Building Blocks] of Markdown"
date:   2020-08-01 16:09:00 -0300
categories: building blocks, markdown, learn programming
---
### What is markdown?

Markdown is a lightweight markup language used to create rich text using a plain text editor. It is often used for formatting readme files and for creating static webpages using Jekyll. Some of its popular cousins form the markup family are HTML and XML. 

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

For a more complete list consider visiting [Codebase](https://support.codebasehq.com/articles/tips-tricks/syntax-highlighting-in-markdown).

By the way this page was written using markdown and rendered to HTML using Jekyll. 

Comments welcome!

{% include disqus.html %}
