---
tags:
  - UPA
aliases:
  - owl
---
OWL is an [[Ontology|ontology]] language that expands on [[Resource Description Framework Scheme|RDFS]] with advanced properties and is used for definitions of complex [[Ontology|ontologies]]. The name space is defined [online](http://www.w3.org/2002/07/owl#) and uses prefix `owl`.
## Classes
Combination with [[Resource Description Framework Scheme|RDFS]]. A class is only defined using logic conditions, such as:
- Class identifier
- Enumeration of instances
- Limiting properties
- Unification or intersection of two or more classes
- Supplement
An example of definition can be done either in Turtle:
```
foaf:Person rdf:type owl:Class .
```
By Turtle with prefixes:
```
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> . 
@prefix owl: <http://www.w3.org/2002/07/owl#> . 
@prefix foaf:<http://xmlns.com/foaf/0.1/>. 

foaf:Person rdf:type owl:Class . 
foaf:Person a owl:Class .
```
By XML:
```
<owl:Class rdf:about="&foaf;Person"/>
```
or:
```
<rdf:Description rdf:ID="Person">
	<rdf:type resource="&owl;Class">
</rdf:Description>
```
Other operations over classes can be `owl:equivalentClass` and `owl:disjointWith`.
## Properties
Properties can be defined by a RDFA constructor:
```
<owl:ObjectProperty rdf:ID="studuje"> 
	<rdfs:domain rdf:resource="#Student"/> 
	<rdfs:range rdf:resource="#Obor"/> 
</owl:ObjectProperty>
```
And relations between properties are done through `owl:equivalentProperty`, `owl:inverseOf`, such as:
```
<owl:ObjectProperty rdf:ID="maStudenta"> 
	<owl:inverseOf rdf:resource="#studuje"/> 
</owl:ObjectProperty>
```