---
ID: 634
post_title: 'All Available RDF Classes &#038; Properties'
author: iurianu
post_excerpt: ""
layout: post
permalink: >
  https://purls.site/structured-data/ontology/all-available-rdf-classes-properties/
published: true
post_date: 2018-07-20 16:19:28
---
<h4>Classes</h4>

rdfs:Class, owl:Class
owl:DeprecatedClass, 
skos:Collection, 
skos:Concept, 
skos:ConceptScheme, 
rdf:Description, 
skosxl:Label, 
rdf:List
owl:Nothing, 
skos:OrderedCollection, 
rdf:Property 
- owl:AnnotationProperty
- owl:DatatypeProperty
- owl:FunctionalProperty
- owl:InverseFunctionalProperty
- owl:ObjectProperty
- owl:SymmetricProperty
- owl:TransitiveProperty
- owl:OntologyProperty
- owl:DeprecatedProperty
- owl:NegativePropertyAssertion
owl:Restriction, 
owl:Thing

<h4>Properties</h4>

skos:altLabel, skosxl:altLabel, 
skos:broadMatch, 
skos:broader, 
skos:broaderTransitive, 
skos:changeNote, 
skos:closeMatch,
rdfs:comment 
skos:definition 
skos:editorialNote,
skos:exactMatch, 
skos:example, 
skos:hasTopConcept, 
skos:hiddenLabel, skosxl:hiddenLabel, 
skos:historyNote, 
skos:inScheme, 
skosxl:labelRelation, 
skosxl:literalForm, 
skos:mappingRelation, 
skos:member, 
skos:memberList, 
skos:narrowMatch, 
skos:narrower, 
skos:narrowerTransitive, 
skos:notation, 
skos:note, 
skos:prefLabel, skosxl:prefLabel, 
skos:related, 
skos:relatedMatch, 
skos:scopeNote, 
skos:semanticRelation, 
skos:topConceptOf

<h4>Property Constructs</h4>

rdfs:subPropertyOf
rdfs:domain
rdfs:range (may appear on owl:DataRange)
owl:assertionProperty
owl:sameAs
owl:differentFrom
owl:distinctMembers (on owl:AllDifferent)

<h4>Property Relations</h4>

owl:equivalentProperty
owl:inverseOf
rdf:first (used on rdf:List)
df:rest (used on rdf:List)
owl:sourceIndividual
owl:targetIndividual

<h4>Property Constraints</h4>

rdf:type
owl:allValuesFrom, 
owl:someValuesFrom, 
owl:backwardCompatibleWith
owl:incompatibleWith 

<h4>Axioms</h4>

rdf:about, 
owl:complementOf, 
rdf:datatype, 
owl:disjointWith, 
owl:equivalentClass, 
owl:hasValue, 
rdf:ID, 
owl:imports
owl:intersectionOf, 
owl:maxCardinality, 
owl:minCardinality, 
owl:oneOf, 
rdf:resource,
owl:onProperty, 
rdf:parseType, 
rdfs:subClassOf, 
owl:unionOf
owl:priorVersion
owl:versionInfo

<h4>Datatypes</h4>

rdfs:Literal
rdf:XMLLiteral
xsd:string
xsd:normalizedString,
xsd:token, 
xsd:language, 
xsd:NMTOKEN, 
xsd:Name,
xsd:NCName
xsd:boolean
xsd:decimal, 
xsd:float, 
xsd:double
xsd:integer, 
xsd:positiveInteger
xsd:nonPositiveInteger, 
xsd:negativeInteger, 
xsd:nonNegativeInteger, 
xsd:long,
xsd:int, 
xsd:short, 
xsd:byte, 
xsd:unsignedLong, 
xsd:unsignedInt, 
xsd:unsignedShort, 
xsd:unsignedByte
xsd:dateTime, 
xsd:time, 
xsd:date, 
xsd:gYearMonth,
xsd:gYear, 
xsd:gMonthDay, 
xsd:gDay, 
xsd:gMonth
xsd:hexBinary, 
xsd:base64Binary
xsd:anyURI