---
tags:
  - UPA
aliases:
  - web scrapping
---
Web (internet) contains an enormous amount of data hidden within web pages. This data can be extracted, aggregated, analysed and more of which outcome can be useful result either for research or commercial use. The issue is extracting this data as modelling, statistics and other fields require structured data, which is difficult to do as web pages do not have a unified structure or value representation.
## Problem
The problem thus boils down to collection of source data, searching and extraction of data and storing of this data into structured format that can be used further.
## Architecture
The basic architecture of a system that can solve the problem is thus:
```
WWW Pages -> HTTP Client -> Parser -> Wrapper -> Structured Data
```
The main three components of this chain are:
- **WWW Pages** - Target web pages for extraction on the web.
- **HTTP client** - Downloads the web page source code from the webserver hosting the pages.
- **Parser** - Transforms the web pages that is most probably in HTML into a usable data structure like an document model of the HTML document.
- **Wrapper** (Extractor) - Searches through the document model for the specified target values and exports them as structured data.
- **Structured Data** - The pipeline result in one of many formats such as JSON, XML, CSV, TSV, etc.
### Languages and Libraries
This extraction can be done in one of many ways and languages with many different libraries, such as:
- **Shell** - A crude but functional way of extraction. Can use commands such `wget`, `curl`,`cat`,`grep`,`sed`,`awk`, etc.
- **Python** - A more modern and dynamic way of extraction. Python allows for more complex and object oriented way of interacting with the pages and their representations. Amongst useful libraries that help with extraction are `urllib` and `beautifulsoup`.
- **Java** - Less dynamic, but still object oriented and modern way of extraction. A useful library in Java is `jSoup`.
### Limitation
Limitations of simple implementations can be many from login forms to redirections. It is possible work around these issues, but it is complicated.
## Models
There are several ways to model and work with HTML documents, such as:
- **A string of symbols**
	- Simple implementation, quick, scalable
	- [[Regular Expressions]], HTLR wrappers
- **A string of tokens**
	- Lexical analysation of tags, entities, text, etc.
	- HLRT wrappers
- **Hierarchic models**
	- Most commonly [[Document Object Model|DOM]]
## Wrapper
A wrapper can extract data from any number of data fields in the document. There are many types (classes) of wrappers, such as LR, HLRT, etc. The meaning of the letters is:
- **Head** - Substring before the data block
- **Left** - Left separator for each data field
- **Right** - Right separator for each data filed
- **Tail** - Substring behind the data block
Wrappers most commonly work with [[Document Object Model|DOM]] models.
## Browser Automation
Another way of working through webpages and their contents, that is connected to automated testing is browser automation. This method, instead of only downloading the web page as a document, simulates a browser and interactions with it. This can be useful for complex web pages and previous issues such as login pages.
Libraries and services that implement such functionality are for examples `Mechnical Soup`, `Puppeteer`, `Playwright` and more.