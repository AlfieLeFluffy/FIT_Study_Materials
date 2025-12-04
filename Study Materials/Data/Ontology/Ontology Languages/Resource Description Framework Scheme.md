---
tags:
  - UPA
aliases:
  - RDF Scheme
  - RDF scheme
  - RDFS
---
A semantic expansion of [[Resource Description Framework|RDF]] and basically an (meta) [[Ontology|ontology]]. It allows for definition of:
- Classes
- Binary relations
- Hierarchy of classes and relations
Definition are done in [[Resource Description Framework|RDF]] statements (trios) with use of concepts and relations from RDFS. It uses a namespace with the prefix `rdfs` and is defined [online](http://www.w3.org/2000/01/rdf-scheme#).
## Classes
Classes are set to a resource using `rdf:type`, such as `school:Person rdf:type rdfs:Class`. The inherited classes are then defined as `school:Student rdfs:subClassOf school:Person`.
## Properties
Properties of instance are set through `rdfs:Property`, such as `school:isEnrolled rdf:type rdfs:Property`. Some extending properties are done as:
- `rdfs:Range` sets types of objects (range of values).
	- `school:isEnrolled rdfs:range school:course`
- `rdfs:Domain` sets types subjects (definition field).
	- `school:isEnrolled rdfs:domain school:Student`
- `rdfs:SubPropertyOf` set the sub-property of a property.