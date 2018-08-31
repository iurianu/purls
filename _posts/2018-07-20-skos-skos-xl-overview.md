---
ID: 597
post_title: 'SKOS &#038; SKOS-XL Overview'
author: iurianu
post_excerpt: ""
layout: post
permalink: >
  https://purls.site/structured-data/ontology/skos-skos-xl-overview/
published: true
post_date: 2018-07-20 11:28:54
---
<figure class="right-thirty"><a href="http://purls.site/wp-content/uploads/2018/07/Semantic-Web.jpg"><img src="http://purls.site/wp-content/uploads/2018/07/Semantic-Web.jpg" alt="Semantic Web Logo" width="400" height="400" class="alignnone size-full wp-image-603" /></a></figure>

<em>SKOS</em> (Simple Knowledge Organization System) is a common data model for sharing and linking knowledge organization systems via the Semantic Web.

<em>SKOS-XL</em> (Simple Knowledge Organization System eXtension for Labels) defines an extension for the Simple Knowledge Organization System, providing additional support for describing and linking lexical entities.

<h4>Namespace:</h4>
<dl>
<dt>skos</dt> <dd><a target="_blank" href="http://www.w3.org/2004/02/skos/core#">http://www.w3.org/2004/02/skos/core#</a></dd>
<dt>skosxl</dt> <dd><a target="_blank" href="http://www.w3.org/2008/05/skos-xl#">http://www.w3.org/2008/05/skos-xl#</a></dd>
</dl>
<h4>Authors:</h4>
<ol class="pointed">
<li><cite>Alistair Miles</cite>, STFC Rutherford Appleton Laboratory / University of Oxford</li>
<li><cite>Sean Bechhofer</cite>, University of Manchester</li>
</ol>

<hr>

Classes: <a href="#Collection">Collection</a>, <a href="#Concept">Concept</a>, <a href="#ConceptScheme">Concept Scheme</a>, <a href="#Label">Label</a>, <a href="#OrderedCollection">Ordered Collection</a>

Properties: <a href="#altLabel">altLabel</a>, <a href="#broadMatch">broadMatch</a>, <a href="#broader">broader</a>, <a href="#broaderTransitive">broaderTransitive</a>, <a href="#changeNote">changeNote</a>, <a href="#closeMatch">closeMatch</a>, <a href="#definition">definition</a>, <a href="#editorialNote">editorialNote</a>, <a href="#exactMatch">exactMatch</a>, <a href="#example">example</a>, <a href="#hasTopConcept">hasTopConcept</a>, <a href="#hiddenLabel">hiddenLabel</a>, <a href="#historyNote">historyNote</a>, <a href="#inScheme">inScheme</a>, <a href="#labelRelation">labelRelation</a>, <a href="#literalForm">literalForm</a>, <a href="#mappingRelation">mappingRelation</a>, <a href="#member">member</a>, <a href="#memberList">memberList</a>, <a href="#narrowMatch">narrowMatch</a>, <a href="#narrower">narrower</a>, <a href="#narrowerTransitive">narrowerTransitive</a>, <a href="#notation">notation</a>, <a href="#note">note</a>, <a href="#prefLabel">prefLabel</a>, <a href="#related">related</a>, <a href="#relatedMatch">relatedMatch</a>, <a href="#scopeNote">scopeNote</a>, <a href="#semanticRelation">semanticRelation</a>, <a href="#topConceptOf">topConceptOf</a>

<hr>

<h3>Classes</h3>
<dl id="Collection">
<dt>Collection</dt>
<dd>Label: Collection</dd>
<dd>URI: <a href="http://www.w3.org/2004/02/skos/core#Collection">skos:Collection</a></dd>
<dd>Disjoint classes: <ol class="pointed"><li><a href="#Concept">skos:Concept</a></li><li><a href="#ConceptScheme">skos:ConceptScheme</a></li></ol></dd>
<dd>Collections are useful where a group of concepts shares something in common, and it is convenient to group them under a common label, or where some concepts can be placed in a meaningful order.</dd>
</dl>
<dl id="Concept">
<dt>Concept</dt>
<dd>Label: Concept</dd>
<dd>URI: <a href="http://www.w3.org/2004/02/skos/core#Concept">skos:Concept</a></dd>
<dd>Disjoint classes: <ol class="pointed"><li>skos:Collection</li><li>skos:ConceptScheme</li></ol></dd>
<dd>A SKOS concept can be viewed as an idea or notion; a unit of thought. <br>The notion of a SKOS concept is useful when describing the conceptual or intellectual structure of a knowledge organization system, and when referring to specific ideas or meanings established within a KOS.</dd>
</dl>
<dl id="ConceptScheme">
<dt>ConceptScheme</dt>
<dd>Label: Concept Scheme</dd>
<dd>URI: <a href="http://www.w3.org/2004/02/skos/core#Concept">skos:ConceptScheme</a></dd>
<dd>Disjoint classes: <ol class="pointed"><li>skos:Collection</li><li>skos:Concept</li></ol></dd>
<dd>A SKOS concept scheme can be viewed as an aggregation of one or more SKOS concepts. <br>Semantic relationships (links) between those concepts may also be viewed as part of a concept scheme.</dd>
</dl><dl id="Label">
<dt>Label</dt>
<dd>Label: Label</dd>
<dd>URI: <a href="http://www.w3.org/2008/05/skos-xl#Label">skosxl:Label</a></dd>
<dd>Super-classes: <ol class="pointed"><li>restriction on <a href="http://www.w3.org/2008/05/skos-xl#literalForm">skosxl:literalForm</a> cardinality exactly 1</li></ol></dd>
<dd>Disjoint classes: <ol class="pointed"><li>skos:Collection</li><li>skos:Concept</li><li>skos:ConceptScheme</li></ol></dd>
<dd>The class Label is a special class of lexical entities, and an instance of the class skosxl:Label is a resource and may be named with a URI. <br>An instance of the class skosxl:Label has a single literal form. <br>This literal form is an RDF plain literal (which is a string of UNICODE characters and an optional language tag).</dd>
</dl>
<dl id="OrderedCollection">
<dt>OrderedCollection</dt>
<dd>Label: Ordered Collection</dd>
<dd>URI: <a href="http://www.w3.org/2004/02/skos/core#OrderedCollection">skos:OrderedCollection</a></dd>
<dd>Super-classes: <ol class="pointed"><li>skos:Collection</li></ol></dd>
<dd>SKOS concept collections are labeled and/or ordered groups of SKOS concepts. <br>Collections are useful where a group of concepts shares something in common, and it is convenient to group them under a common label, or where some concepts can be placed in a meaningful order.</dd>
</dl>

<hr>

<h3>Properties</h3>
<dl id="altLabel">
<dt>altLabel</dt>
<dd>Label: alternative label</dd>
<dd>URI: <a href="http://www.w3.org/2004/02/skos/core#altLabel">skos:altLabel</a>, <a href="http://www.w3.org/2008/05/skos-xl#altLabel">skosxl:altLabel</a></dd>
<dd>Super-properties: <ol class="pointed"><li><a href="http://www.w3.org/2000/01/rdf-schema#label">rdfs:label</a></li></ol></dd>
<dd>The preferred and alternative labels are useful when generating or creating human-readable representations of a knowledge organization system. <br>These labels provide the strongest clues as to the meaning of a SKOS concept.</dd>
</dl>
<dl id="broadMatch">
<dt>broadMatch</dt>
<dd>Label: has broader match</dd>
<dd>URI: <a href="http://www.w3.org/2004/02/skos/core#broadMatch">skos:broadMatch</a></dd>
<dd>Super-properties: <ol class="pointed"><li>skos:broader</li><li>skos:mappingRelation</li></ol></dd>
<dd>Inverse of:	<ol class="pointed"><li>skos:narrowMatch</li></ol></dd>
<dd>The properties <em>skos:broadMatch</em> and <em>skos:narrowMatch</em> are used to state a hierarchical mapping link between two concepts.</dd>
</dl>
<dl id="broader">
<dt>broader</dt>
<dd>Label: has broader</dd>
<dd>URI: <a href="http://www.w3.org/2004/02/skos/core#broader">skos:broader</a></dd>
<dd>Super-properties: <ol class="pointed"><li>skos:broaderTransitive</li></ol></dd>
<dd>Inverse of:	<ol class="pointed"><li>skos:narrower</li></ol></dd>
<dd>The properties <em>skos:broader</em> and <em>skos:narrower</em> are used to assert a direct hierarchical link between two SKOS concepts.</dd>
</dl>
<dl id="broaderTransitive">
<dt>broaderTransitive</dt>
<dd>Label: has broader transitive</dd>
<dd>URI: <a href="http://www.w3.org/2004/02/skos/core#broaderTransitive">skos:broaderTransitive</a></dd>
<dd>Super-properties: <ol class="pointed"><li>skos:semanticRelation</li></ol></dd>
<dd>Inverse of:	<ol class="pointed"><li>skos:narrowerTransitive</li></ol></dd>
<dd>Some applications need to make use of both direct and indirect hierarchical links between concepts, for instance to improve search recall through query expansion. For this purpose, the properties <em>skos:broaderTransitive</em> and <em>skos:narrowerTransitive</em> are provided.</dd>
<dd>Type: Transitive Property</dd>
</dl>
<dl id="changeNote">
<dt>changeNote</dt>
<dd>Label: change note</dd>
<dd>URI: <a href="http://www.w3.org/2004/02/skos/core#changeNote">skos:changeNote</a></dd>
<dd>Super-properties: <ol class="pointed"><li>skos:note</li></ol></dd>
<dd>Notes are used to provide information relating to SKOS concepts. There is no restriction on the nature of this information, e.g., it could be plain text, hypertext, or an image; it could be a definition, information about the scope of a concept, editorial information, or any other type of information.</dd>
</dl>

skos:closeMatch
skos:definition
skos:editorialNote
skos:exactMatch
skos:example
skos:hasTopConcept
skos:hiddenLabel
skosxl:hiddenLabel
skos:historyNote
skos:inScheme
skosxl:labelRelation
skosxl:literalForm
skos:mappingRelation
skos:member
skos:memberList
skos:narrowMatch
skos:narrower
skos:narrowerTransitive
skos:notation
skos:note
skos:prefLabel
skosxl:prefLabel
skos:related
skos:relatedMatch
skos:scopeNote
skos:semanticRelation
skos:topConceptOf