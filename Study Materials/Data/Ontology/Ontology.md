---
tags:
  - UPA
aliases:
  - ontology
---
Ontology are **dictionaries of the semantic web**, but originally the word ontology had a more broad meaning from philosophy. It is a tool for **sharing definitions** (semantics) of terms, that appear in the target field. They define basic terms of the modelled world and relations between them and are shared and reused. 
## Usage
Amongst common use cases of ontologies are:
- Understanding between **people** and experts
- Understanding between **computer** applications
	- Definitions of each URI in a semantic web
	- Option to integrate data from different sources
- Design of **knowledge applications**
## Types
Some common types of ontologies are:
- **Terminology** (lexical)
	- Terms and their relations (taxonomy)
	- For example WordNet
- **Generic**
	- Regularities and relations between common terms
	- Upper ontology
	- For example SUMO
- **Domain**
	- Specific field (economy, biology, etc.)
- **Application**
	- For a specific application
## Elements
Elements of an ontology are:
- **Classes**/**Concepts**
- **Objects**/**Instances**
- **Relations**/**Roles**/**Attributes**
- **Facets**
- **Primitive Data Types**
- **Axioms**/**Rules**
### Class/Concepts
[[Set|Sets]] of specific objects without procedural methods. Classes are defined and primitive. Classes can inherit often even multiple times (multi-layered inheritance).
### Object/Instance
Specific objects from real life. Also known as individual. An object does not have to be an instance of a class. Because of how ontologies are used, it is not commonly used as they represent specific data.
### Relation/Role/Attribute
The concept of relation in ontologies is different from [[Object Data Model]] or [[Object-Oriented Programming]], etc. In ontologies a relation is an attribute (property) and is a separately defined element. Usually the relation is binary.
Inheritance in relations is possible and the parent relation contains all elements of the child relations.
Function is a special kind of relation, where the value of argument n is clearly defined by previous n-1 arguments.
### Primitive Values/Data Types
An argument (properties) of the relation can be a primitive value, but not object. These values can be of types such as:
- Number
- String
- Enumeration
We can think of these as data-type classes (data type) and data-type instance (values). Data-type properties are usually declared as functional (they have only one value).
## Languages
Ontology languages are a way to define ontologies in a written/structured way. The most common once are [[Resource Description Framework Scheme]] and [[OWL]].
### RDF Scheme
![[Resource Description Framework Scheme]]
### OWL
![[OWL]]
## Existing Ontologies
There is a high emphasis for maximal use of existing ontologies. It is possible to combine concepts and properties from different ontologies. An overview of ontologies can be found [here](https://lov.linkeddata.es/dataset/lov/). Some notables one are:
### Dublin Core
Document metadata most commonly used in librarianship. It is used to define properties of documents, such as:
```
<rdf:Description rdf:about="http://www.w3schools.com"> 
	<dc:description>W3Schools</dc:description> 
	<dc:publisher>Refsnes Data as</dc:publisher> 
	<dc:date>2008-09-01</dc:date> 
	<dc:type>Web Development</dc:type> 
	<dc:format>text/html</dc:format> 
	<dc:language>en</dc:language> 
</rdf:Description>
```
### Friend-of-a-friend
An ontology used for description of a people and their relations. It contains classes for description of 
- People, such as:
	- `foaf:Agent`
	- `foaf:Person`
- Properties, such as:
	- `foaf:name`
	- `foaf:known`
### SKOS
Simple Knowledge Organization System allows for organization of terms in some domain. It contains classes for things such as concepts, relations between them, etc.
### Scheme.org
Used mainly for annotating of web pages and basic ontologies for many common domains. 
