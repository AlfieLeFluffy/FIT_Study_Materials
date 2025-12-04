---
tags:
  - UPA
aliases:
  - resource description framework
  - RDF
---
The goal of RDF is to represent structured data, its meaning (semantics) and to allow for sharing of data and their semantics across applications. The issues with common representations in information systems are:
- [[Relation Data Model]]/[[Object Data Model]]/[[NoSQL]] databases are tied to the application.
- Public APIs + [[Serialization and Deserialization]] (JSON, XML) do not have a predefined semantics.
## Fact Representation
RDF allows for representation of elementary statements that represent data/facts. It has a [[Oriented Graph|oriented graph]] structure and each statements are interconnected using URI. These facts can be serialized and stored in file for transfer and can be written using formats such as XML.
### Statement
The basic element in RDF is a trio **subject-predicate-object**, which is the basic statement. An example of such statement can be *"autor of document X is person Y,"* where:
- **Subject**: *document X*
- **Predicate**: *authored by*
- **Object**: *person Y*
Each part of the statement (resources) are represented using URI or literal (only object). If we would take the previous example then it could look something like:
```
http://novak.cz/documentX == http://novak.cz/authored-by => personY
```
The URI used can be either:
- Custom data/URI
	- For example `http://fit.vut.cz/student/938272`
	- Usually has a common prefix.
- Existing data in public knowledge bases
	- For example `hhtp://dbpedia.org/resource/Berlin`
- Structured dictionary [[Ontology]]
	- URI for predicate, type, class, object, etc.
- Inbuilt
	- Such as `rdf:type`
### Graf
A RDF [[Graph|graph]] can be divided into the statement trio subject-predicate-object. Subjects and objects are the vertexes and predicates are the edges. Both subjects and predicates are URI. For examples:
- `doc:` is a URI prefix that expands into for example `doc:name => http://my.docs.com/#name`
Object can be both URI and a literal of one of many types.
### Semantics
RDF data can interconnected with metadata ([[Ontology]], schemes) using predicates such as `rdf:type(http://www.w3.org/1999/02/22-rdf-syntax-ns#type)`. Definition of metadata is also done using RDF and it is possible but not necessary to connect data and metadata into one graph.
## Storage and Transfer
RDF data is usually stored in databases. Examples of such databases can be:
- Local storage:
	- [Virtuoso](http;//virtuoso.openlinksw.com/)
	- [RDF4J](http://rdf4j.org/) (originally Sesame)
- Global storage (public knowledge bases):
	- [DBPedia](http://dbpedia.org)
	- [WikiData](https://www.wikidata.org/)
The data is split into the RDF trio and stored in internal structures. These databases then can be queried using languages such as **SPARQL**.
### Serialization
There are several ways of [[Serialization and Deserialization]] for RDF, such as:
- **RDF/XML** using standard W3C
- **N-triples** using standard N3
- **Turtle** which is a subset of N3
### Open Data
Serialized RDF data as a tool for publishing open (interconnected data). These include such datasets like found on [data.europa.eu](data.europa.eu). It is possible to import this data into a local RDF storage, connected with other datasets and then used for querying using **SPARQL**. Alternatively, there also exist public **SPARQL** endpoints (APIs).
## RDF and Web
Semantic annotation is used for understanding web pages and is a connection between HTML and concepts of [[Semantic Web]] (URI). There are several standards and integrations for semantic annotation, such as:
- **RDFa**
- **HTML5 Microdata**
- **JSON-LD**
### Google Structured Data
Google processes the structured data on HTML pages both in RDFa and JSON-LD formats, supports many [[Ontology|ontologies]] from Schema.org.