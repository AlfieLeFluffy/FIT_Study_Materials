---
tags:
  - UPA
aliases:
  - XML
---
A text-based mark-up language file format for the explicit use on the internet. It is a *web standard* and it is intendent for platform-independent storing and transferring of arbitrary data.
## Format
An XML document consists of:
- **Declaration** is a header type element consisting of the version, encoding and other information that a system parsing the file might find useful.
- **Elements** are logical parts with a name, attributes and some content between the start tag and the end tag or is left empty.
- **Tags** are mark-up constructs that begin with *<* and end with *>* and designate the start or end of a logical segment. 
- **Attributes** are used for name-value pairs that exist within elements such as encoded chards, CDATA, processor, directives, etc.
A correct XML file must also be *well-formed* (syntactically correct) and *valid* (semantically correct). A valid document must follow a specific XML scheme.
## Scheme
The content of an XML document is restricted by an XML scheme. An XML scheme is described by an external XML document. In order to understand an XML file structure, the scheme is required.
### Types
There are several types of XML scheme documents:
- **Document Type Definition** (DTD): from SGML and is deprecated.
- **W3C XML Scheme**: de-facto standard in XML validation.
- **RELAX NG**: a strong language, the ability to validate text nodes.
- **Schematron**: rule-based with [[XPath]] rules, also quite strong.
## Types
There are two main types of XML documents:
- **Data-centric XML** documents
	- Mainly used for exporting/importing collections of data with complex structures.
	- The order of the elements is unimportant.
- **Document-centric XML** documents
	- Mainly used for text documents that are marked-up as XML.
	- Utilized for rendering of visual outputs.
	- Has irregular structure and the order is important.
## XPath
![[XPath]]
## XQuery
![[XQuery]]
## Adoption
XML was adopted in many ways such as:
- **Databases**
	- Most of the current databases support XML data.
	- XML data is stored as structured/object data and may be queried.
- **Native XML Databases**
	- Data model is based on the [[Document Object Model]].
	- Queries and operations over XML data are fast.
- **XML Wrappers/Mappers**
	- To access XML data in relation way through query in [[Structured Query Language|SQL]] etc.
- **Middleware Utilizing XML**
	- To communicate between application components in XML format.
	- The XML can be utilized as platform-independent data format.
	- The ability to implement VETRO features (Validity, Enrichment, Transformations, Content-based Routing).
- **XML Data Binding**
	- The mapping of XML to object data and vice versa.
	- To provide a persistence of the objects.
