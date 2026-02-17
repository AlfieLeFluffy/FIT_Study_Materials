---
tags:
  - UPA
aliases:
  - document object model
  - DOM
---
HTML code can be represented as a [[Tree|tree]] of objects, with each object being of different type.
## DOM Tree
A DOM tree always has only one root node of type `Document`. It has one child node of type `Element`, which is the document root element.
### Element
A HTML element is defined by its tags, with any other elements being part of the element being its child elements both in HTML and in the DOM. An element can also have other child nodes that are not other elements, such as text, pictures and other common types.
## Navigation
There are many ways to navigate a DOM tree depending on how and what you are searching retrieving. These include:
- A standard method and attributes for DOM classes `Document` and `Element` are:
	- Search elements: `getElementById()`, `getElementsByTagName()`
	- Navigation inside the tree: `parentNode`, `childNodes`, etc.
	- Access to the contents: `textContent`
- CSS selectors:
	- Output is always a [[Set|set]] of elements.
	- Includes CSS classes and information, such as: `#main`, `header`, `.info`, etc.
- [[XPath]]:
	- Output is also a [[Set|set]] of elements.
	- An example can be: `*[@id="main"]//table/tr[position()>3]`
## Practical Use
A fully functional HTML 5 DOM parser is complicated to find and pretty much only exists in web browser. In practice it often simplifies parsers with their own interfaces like in libraries, such as `BeautifulSoup` and `jSoup`. 