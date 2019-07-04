# Getting Started with Python

### Simple Scrapy project
Based on [Scrapy tutorial](https://docs.scrapy.org/en/latest/intro/tutorial.htmltutorial).

### Prerequisites
Install `pipenv` like package manager.

### Install

To install the project dependencies you only need to run:

```
pipenv install
```

### Running project

```
pipenv run scrapy crawl quotes
```

___

### Getting start with Python
**Helpers** 
```
pipenv install beautifulsoup4
pipenv install ipython
```

### Environment configuration
Getting installed dir where the python information was installed
```
pipenv --venv
```
Take the path and insert it in:
```
File > Settings > Project > Project Interpreter
```
3) Click at `three dots` on right site > Add
4) Put dir path and click at `/bin/python`
5) Then confirm

___

### Running the application in terminal
How to execute an application by terminal? Follow next steps:
```
pipenv run scrapy crawl <spider name>
```

---

### Execute scrapy by shell, write the following code in shell terminal
To open the shell, you need to execute the next command in terminal:
```
pipenv run scrapy shell 'http://quotes.toscrape.com/page/1/'
```

Opening the current page in browser by shell:
```
view(response)
```

Checking the current HTML:
```
response.body
```

### Dentro do shell
Open current page by Shell:
```
view(response)
```
Returns an array with title text without tag:
```
response.css('title::text').getall()
```
Returns the first found element based on passed expression:
```
response.css('title::text').get()
``` 

#### Regular expressions
You need to use `.re()` like following example:
```
response.css('title::text').re(r'Q\w+')
```

--- 

### Returning to HANDS-ON
Taking div selectors and taking first element:
```
response.css("div.quote") 
response.css("div.quote")[0]
```

Let's extract `title`, `author` and `tags`:

```
title = quote.css('span.text::text').get()
author = quote.css('small.author::text').get()
tags = quote.css('div.tags a.tag::text).getall()
```

___

### Scraping attributes:
`response.css('li.next a::attr(href)').get()'`