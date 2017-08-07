# Idea Ontology Vocabulary Specification 1.0

## Namespace Document 1 November 2009 - Initial Version

<dl>
<dt>This version:</dt>

<dd><a href="https://github.com/riedlc/IdeaOntology">https://github.com/riedlc/IdeaOntology</a> (<a href="https://github.com/riedlc/IdeaOntology/blob/master/20091101.rdf">rdf</a>)</dd>

<dt>Latest version:</dt>
<dd><a href="https://github.com/riedlc/IdeaOntology">https://github.com/riedlc/IdeaOntology</a> (<a href="https://github.com/riedlc/IdeaOntology/blob/master/20091101.rdf">rdf</a>)</dd>

<dt>Authors:</dt>
<dd><a href="mailto:riedlc[at.]in.tum.de">Christoph Riedl</a>,
<a>Norman May</a>,
<a>Jan Finzen</a>,
<a>Stephan Stathel</a>,
<a>Helmut Krcmar</a></dd>

<dt>Contributors:</dt>
<dd>Members of TEXO and related projects. See <a href="#sec-ack">acknowledgements</a>.</dd>
</dl>

<p>Copyright &copy; 2009-2010 Christoph Riedl, Norman May, Jan Finzen, Stephan Stathel, Helmut Krcmar<br />
  <br />

  <!-- Creative Commons License -->
   <a href="http://creativecommons.org/licenses/by/1.0/"><img alt="Creative Commons License" style="border: 0; float: right; padding: 10px;" src="res/somerights.gif" /></a> 
	 This work is licensed under a <a href="http://creativecommons.org/licenses/by/1.0/">Creative Commons Attribution License</a>. This copyright applies to the Idea Ontology Vocabulary Specification and accompanying documentation in RDF. Regarding underlying technology, the Idea Ontology uses W3C's <a href="http://www.w3.org/RDF/">RDF</a> and <a href="http://www.w3.org/TR/owl-features/">OWL</a> technology, open Web standards that can be freely used by anyone.
	 The design of this website is based on that of the <a href="http://xmlns.com/foaf/spec/">FOAF Vocabulary Specification</a>.</p>

  <hr />


## Abstract

This specification describes the Idea Ontology (IM) using the OWL technology. While most people have an intuitive understanding of what the terms 
<em>idea</em> and <em>innovation</em> mean, a precise and formal definition for the concept of an idea is hard to obtain. Nevertheless, 
it becomes increasingly important to close this gap. Exchanging and analyzing ideas across different software tools and 
repositories is needed to implement the concepts of open innovation and holistic innovation management. The Idea Ontology 
provides a common language to foster interoperability between tools and to support the idea life cycle. 


## Status of This Document
The Idea Ontology has been evolving gradually since its creation in 2008. The current state can now be considered a stable core of classes and properties 
that will not see too much changes in the future. New terms may be added as new requirements emerge,  and consequently this specification 
is an evolving work. The Idea Ontology RDF namespace, by contrast, is fixed and it's identifier is not expected to <a href="#sec-changes">change</a>.

The Idea Ontology specification is produced as part of the <a href="http://theseus-programm.de/en-us/theseus-application-scenarios/texo/">TEXO project</a>, making a contribution towards the creation of a new Internet-based knowledge infrastructure that will allow faster and more effective processing and use of online knowledge in future.

The authors welcome comments on this document, preferably via email to the authors.

As usual, see the <a href="#sec-changes">changes</a> section for details of the changes in this version of the specification.


## Table of Contents

<ul>
<li><a href="#sec-glance">IM at a glance</a></li>
<li><a href="#sec-intro">Introduction</a></li>
<li><a href="#sec-sw">The Semantic Web</a></li>
<li><a href="#sec-imsw">IM and the Semantic Web</a></li>
<li><a href="#sec-basicidea">The Basic Idea</a></li>
<li><a href="#sec-crossref">IM cross-reference: Listing IM Classes and Properties</a></li>
<li><a href="#sec-ack">Acknowledgments</a></li>
<li><a href="#sec-disclaimer">Copyright Disclaimer</a></li>
<li><a href="#sec-changes">Recent Changes</a></li>
</ul>



## IM at a glance
 
 <p>An a-z index of IM terms, by class (categories or types) and
  by property.</p>

<p>Classes: <a href="#term_CoreIdea">CoreIdea</a> |  <a href="#term_IdeaRealization">IdeaRealization</a> |  <a href="#term_Origin">Origin</a> |   <a href="#term_Status">Status</a>

</p>
<p>Object properties: <a href="#term_hasAttachement">hasAttachement</a> |  <a href="#term_hasCreator">hasCreator</a> |  <a href="#term_hasForum">hasForum</a> |  <a href="#term_hasOrigin">hasOrigin</a> | 
<a href="#term_hasRating">hasRating</a> |  <a href="#term_hasRealization">hasRealization</a> |  <a href="#term_hasStatus">hasStatus</a> |  <a href="#term_hasTagging">hasTagging</a> |  
<a href="#term_hasTopic">hasTopic</a> |  <a href="#term_isNewVersionOf">isNewVersionOf</a>

</p>

<p>Data properties: <a href="#term_abstract">abstract</a> |  <a href="#term_date">date</a> |  <a href="#term_description">description</a> |  <a href="#term_title">title</a> |  
<a href="#term_version">version</a>

</p>




### Core Idea Basics

<ul>
<li><a href="#term_title">title</a></li>
<li><a href="#term_abstract">abstract</a></li>
<li><a href="#term_description">description</a></li>
<li><a href="#term_date">date</a></li>
<li><a href="#term_hasAttachment">hasAttachment</a></li>
<li><a href="#term_hasCreator">hasCreator</a></li>
<li><a href="#term_hasForum">hasForum</a></li>
<li><a href="#term_hasOrigin">hasOrigin</a></li>
<li><a href="#term_hasRating">hasRating</a></li>
<li><a href="#term_hasRealization">hasRealization</a></li>
<li><a href="#term_hasStatus">hasStatus</a></li>
<li><a href="#term_hasTagging">hasTagging</a></li>
<li><a href="#term_hasTopic">hasTopic</a></li>
<li><a href="#term_isNewVersionOf">isNewVersionOf</a>&nbsp;&nbsp;</li>
</ul>
  
![Overview of Idea Ontology concepts](https://github.com/riedlc/IdeaOntology/blob/master/res/IdeaOntologyOverview.png "Overview of Idea Ontology concepts")

## Example

Here is a very basic document describing a simple idea:

```
<#idea123> a im:CoreIdea ; 
	dc:title "Calculate environmental sustainability based on bill of materials." ; 
	im:hasForum <#forum idea123> . 
<#forum idea123> a sioc:Forum . 
&lt;http://en.wikipedia.org/wiki/Market&gt; a skos:Concept ; 
	skos:prefLabel "Market"@en . 
&lt;http://en.wikipedia.org/wiki/Customer&gt; a skos:Concept ; 
	skos:prefLabel "Customer"@en . 
<#item101> a sioc:Item ; 
	sioc:has container <#forum idea123> ; 
	im:hasTopic <http://en.wikipedia.org/wiki/Market> ; 
	sioc:content "Automotive industries" . 
<#item102> a sioc:Item ; 
	sioc:has container <#forum idea123> ; 
	im:hasTopic <http://en.wikipedia.org/wiki/Customer> ; 
	sioc:content "Engineering departments of automobile manufacturers" .
```

  <p>The example illustrates how the combination of <a href="#term_CoreIdea">im:CoreIdea</a>, 
  <a href="http://rdfs.org/sioc/spec/#term_Item" target="sioc">sioc:Item</a>, and <a href="http://www.w3.org/TR/skos-reference/#Concept" target="skos">skos:Concept</a> can be used to represent detailed idea submission forms 
  in a semantically enriched way. We model descriptive arguments as <a href="http://rdfs.org/sioc/spec/#term_Item" target="sioc">sioc:Items</a> 
  that are attached to an idea and further linked to a <a href="http://www.w3.org/TR/skos-reference/#Concept" target="skos">skos:Concept</a> through the 
  <a href="term_hasTopic">hasTopic</a> relationship that defines the semantic meaning of the 
  argument. As <a href="http://rdfs.org/sioc/spec/#term_Item" target="sioc">sioc:Items</a> are modeled as <a href="http://www.w3.org/TR/rdf-primer/" target="rdf">rdf:Resources</a> it is possible to assign a rating to them.</p>



  <!-- ================================================================== -->


## Introduction: IM Basics

### The Semantic Web

<blockquote>

<em>
  To a computer, the Web is a flat, boring world, devoid of meaning. 
  This is a pity, as in fact documents on the Web describe real objects and 
  imaginary concepts, and give particular relationships between them. For 
  example, a document might describe a person. The title document to a house describes a house 
  and also the ownership relation with a person. Adding semantics to the Web involves two things: 
  allowing documents which have information in machine-readable forms, and allowing links to be 
  created with relationship values. Only  when we have this extra level of semantics will we be 
  able to use computer power to help us exploit the information to a greater extent than our own reading.
</em>
<br />
<br />
- Tim Berners-Lee &quot;W3 future directions&quot; keynote, 1st World Wide Web Conference Geneva, May 1994
</blockquote>

### IM and the Semantic Web

<p>
Several benefits can be expected by the use of an ontology. They provide structure to poorly structured 
or unstructured information, realize management support and interdisciplinary communication as a result 
of structuring information, and allow the analysis and comparison of the information represented beyond 
operational data. In addition to these generic benefits of representing information with defined 
ontologies other benefits particular important in the area of representing ideas and innovation 
management can be expected. As more and more idea and innovation platforms appear on the Web, it 
becomes desirable to exchange information between platforms and tools to prevent ideas from residing 
in silos. At the same time, enterprises start to understand the potential benefit from open innovation 
systems and feel the need to open up their internal innovation processes and to integrate innovation 
management tools. The semantics of an organization's specific working context is captured by its local 
or private ontology which serves the purposes of the particular organization. Thus, the need for a 
common language, i.e., a common idea data interchange format or a shared ontology to support the 
interoperability and to improve cross-enterprise collaboration, becomes evident.</p>

<p>
Today, most existing idea portals on the Web are restricted to capabilities like tagging and ordinal 
ratings as the basis for idea analysis. However, we believe that more powerful tools and methods in idea 
portals cannot reveal their full potential until an agreement on the basic concepts of an idea is reached. 
The use of semantic techniques brings with it the possibility to improve end-user efficiency by means of 
automated processing, and to cope with advanced analytical processing of idea metadata through reasoning. 
Thus innovation managers could profit from better structured information, integration and data exchange 
across tools and platforms, and additional semantic reasoning that allows to analyze ideas based on 
related concepts.</p>

<p>
In summary, the main benefits of using an ontology approach for idea management are the ability to 
achieve interoperability and technical integration between tools thus better supporting the idea life 
cycle from idea generation, idea evaluation through to idea implementation across specialized tools as 
well as advanced analysis through semantic reasoning.</p>

### The Basic Idea

  <p>We chose <a href="https://www.w3.org/TR/owl-features/" target="owl">OWL</a> for the development of our ontology 
  and followed a generic ontology development approach. During our reserach we found that neither 
  <a href="http://www.w3.org/RDF/" target="rdf">RDF</a> as well as <a href="http://www.w3.org/TR/rdf-schema" target="rdf">RDFS</a> 
  is not expressive enough to model complex structures like complex classes and relations carrying 
  semantic expressions. As RDFS only supports classes and relations, it is also capable of modeling 
  sub-class concepts and relations, but only simple ones. In the evaluation section, this will be 
  explained with an example. We chose the approach by Noy and McGuinnes (&quot;Ontology development 101: 
  A guide to creating your first ontology&quot;) as it in particular focuses on the reuse of existing 
  ontologies. <a href="http://protege.stanford.edu" target="extern">Prot&eacute;g&eacute;</a> has been used for modeling the Idea 
  To further determine the scope of the ontology, 
  a list of exemplary competency questions that a knowledge base based on the ontology should be able 
  to answer has been designed. The questions have been prepared from the perspective of an innovation 
  manager working with a large pool of ideas.</p>
  
  <ul>
  <li/>Which ideas are in the repository?
  <li/>For which categories have ideas been submitted?
  <li/>Which tags have been used to classify ideas?
  <li/>Which ideas have already been implemented?
  <li/>Which ideas have at least three ratings?
  <li/>Which ideas have at least two or more ratings as well as at least one realization?
  <li/>Which are the most valueable community members by assessing at least three ideas?
  </ul>
  
  <p>The various namespaces used in the ontology are summarized in the following table.</p>
  
<table border="1" rules="all" cellpadding="5">
<tr>
<th>Ontology</th>
<th>Prefix</th>
<th>Short Description</th>
</tr>
<tr>
<td>Idea Ontology</td>
<td>im</td>
<td>The ontology for innovation management introduced here</td>
</tr>
<tr>
<td><a href="http://www.w3.org/RDF" target="rdf">RDF</a></td>
<td>rdf</td>
<td>Resource Description Framework</td>
</tr>
<tr>
<td><a href="http://dublincore.org/documents/dces/" target="dc">Dublin Core</a></td>
<td>dc</td>
<td>The Dublin Core for metadata about resources</td>
</tr>
<tr>
<td><a href="http://xmlns.com/foaf/spec/" target="foaf">FOAF</a></td>
<td>foaf</td>
<td>The Friend of a Friend ontology for describing agents and their relationships</td>
</tr>
<tr>
<td><a href="http://www.holygoat.co.uk/owl/redwood/0.1/tags" target="tagging">Tagging Ontolgy</a></td>
<td>tags</td>
<td>A simple tagging ontology</td>
</tr>
<tr>
<td><a href="http://rdfs.org/sioc/" target="sioc">SIOC</a></td>
<td>sioc</td>
<td>An ontology for (online) communities</td>
</tr>
<tr>
<td><a href="http://www.tvblob.com/ratings/" target="rating">Rating Ontology</a></td>
<td>r</td>
<td>A rating ontology</td>
</tr>
<tr>
<td><a href="http://www.w3.org/2008/05/skos" target="skos">SKOS</a></td>
<td>skos</td>
<td>An ontology for knowledge representation</td>
</tr>
</table>

## IM cross-reference: Listing IM Classes and Properties

  <p>IM introduces the following classes and properties. View
  this document's source markup to see the RDF/XML version.</p>

  
### Classes and Properties (full detail)

<!-- Classes -->

<div class="specterm" id="term_CoreIdea" />
---
#### Class: im:CoreIdea 


<table>
<tr><th>sub-class-of:</th><td> <a href="#term_Resource">rdf:Resource</a></td></tr>
<tr><th>in-range-of:</th><td> <a href="#term_abstract">im:abstract</a> <a href="#term_date">dc:date</a> 
<a href="#term_description">dc:description</a> <a href="#term_title">dc:title</a> <a href="#term_version">im:version</a></td></tr>
<tr><th>in-domain-of:</th><td> <a href="#term_hasForum">im:hasForum</a> 
<a href="#term_hasRealization">im:hasRealization</a> <a href="#term_hasStatus">im:hasStatus</a> <a href="#term_isNewVersionOf">im:isNewVersionOf</a></td></tr>
</table>

<p>
This is the central class of the Idea Ontology. An <code><a href="#term_CoreIdea">im:CoreIdea</a></code> is the entity that holds an idea. To achieve a generic and versatile representation of ideas we chose a hierarchical design with three layers of textual descriptions for a <code><a href="#term_CoreIdea">im:CoreIdea</a></code>: <code><a href="#term_title">dc:title</a></code>, <code><a href="#term_abstract">im:abstract</a></code>, and <code><a href="#term_description">dc:description</a></code>. All three represent a textual description of the idea but vary in length and detail. Thus, our ontology is able to support very simple tools such as electronic brainstorming where an idea usually consists of no more than one sentence, up to more advanced tools that allow longer descriptions. 
It is also possible to extend the description with resources such as images, screenshots, or process diagrams: they can be attached as <code><a href="http://xmlns.com/foaf/spec/#term_Document" target="foaf">foaf:Documents</a></code> using the <code><a href="#term_hasAttachment">im:hasAttachment</a></code> relationship. 
Furthermore, every <code><a href="#term_CoreIdea">im:CoreIdea</a></code> has an associated creation date <code><a href="#term_date">dc:date</a></code> and a <code><a href="#term_version">im:version</a></code> number to allow keeping track of different instances of the same idea by means of the <code><a href="#term_isNewVersionOf">im:isNewVersionOf</a></code> relationship. 
An idea can also have a relationship with <code><a href="http://rdfs.org/sioc/spec/#term_Forum" target="sioc">sioc:Forum</a></code> (using <code><a href="#term_hasForum">im:hasForum</a></code>) and <code><a href="#term_IdeaRealization">im:IdeaRealization</a></code> (using <code><a href="#term_hasRealization">im:hasRalization</a></code>). 
<br/><br/>
Through the sub-classing attributes such <code><a href="#term_hasCreator">im:hasCreator</a></code>, <code><a href="#term_hasRating">im:hasRating</a></code>, and <code><a href="#term_hasTagging">im:hasTagging</a></code> are inherited from <code><a href="#term_Resource">rdf:Resource</a></code>.
</p>


<div class="specterm" id="term_IdeaRealization" />
---
#### Class: im:IdeaRealization

<table>
<tr><th>in-range-of: </th><td> <a href="#term_hasRealization">im:hasRealization</a></td></tr>
<tr><th>in-domain-of: </th><td><em>unspecified (see description below)</em></td></tr></table>

<p>
To support the full innovation life cycle and to allow for incremental innovations of existing products and services the link between ideas and their resulting realizations must be preserved. Moreover, the back-link from a realization to the original idea allows evaluating various performance measures. For example, it would be possible to identify authors of highly successful ideas.
To achieve this tracking across the life cycle our ontology contains an <code><a href="#term_IdeaRealization">im:IdeaRealization</a></code> class which is linked to an <code><a href="#term_CoreIdea">im:CoreIdea</a></code> by means of the <code><a href="#term_CoreIdea">im:hasRealization</a></code> object property. The <code><a href="#term_IdeaRealization">im:IdeaRealization</a></code> class is a placeholder for whatever is an appropriate means of representing an idea's realization. In a product environment this may be a product number. In a software-as-a-service environment the idea realization could link to a description of a Web service, for example, using <a href="http://www.w3.org/TR/wsdl" target="wsdl">WSDL</a>.  
The idea described in an <code><a href="#term_CoreIdea">im:CoreIdea</a></code> may 
be realized as a new product or new service at a later stage of the innovation process. 
This class is used to link an <code><a href="#term_CoreIdea">
im:CoreIdea</a></code> to a realization of that idea.</p>


<div class="specterm" id="term_Origin" />
---
#### Class: im:Origin
<table>
<tr><th>in-range-of:</th><td> <a href="#term_hasOrigin">im:hasOrigin</a></td></tr>
<tr><th>in-domain-of:</th><td> <a href="http://purl.org/dc/elements/1.1/source" target="dc">dc:source</a> <a href="#term_title">dc:title</a></td></tr></table>

<p>As one of our Idea Ontology's main goals is to foster interoperability between various innovation management tools it is necessary to keep track of the application that a given resource originates from. The <code><a href="#term_Origin">im:Origin</a></code> class can be used for this purpose. In this way it can be stated that an idea originates, e.g., from a brainstorming tool, an idea portal on the Web, or another application. 
The application that the <code><a href="#term_Resource">rdf:Resource</a></code> originates from.</p>


<div class="specterm" id="term_Resource" />
---
#### Class: rdf:Resource
<table>
<tr><th>in-range-of:</th><td> <a href="#term_hasCreator">im:hasCreator</a> <a href="#term_hasTagging">im:hasTagging</a>
<a href="#term_hasTopic">im:hasTopic</a></td></tr>
<tr><th>in-domain-of:</th><td> <a href="#term_hasAttachment">im:hasAttachment</a></td></tr></table>

<p>
Innovation related documents share certain common aspects such as having a topic or being rateable. Thus, all innovation related documents have been subsumed 
under the class <code><a href="http://www.w3.org/RDF#Resource" target="rdf">rdf:Resource</a></code>. <br />
Known sub-classes within the context of the Idea Ontology are <code><a href="#term_CoreIdea">im:CoreIdea</a></code>, <code><a href="http://rdfs.org/sioc/spec/#term_Item" target="sioc">sioc:Item</a></code>, and <code><a href="http://xmlns.com/foaf/spec/#term_Document" target="foaf">foaf:Document</a></code>.
</p>


<div class="specterm" id="term_Status" />
---
#### Class: im:Status
<table>
<tr><th>in-range-of:</th><td><a href="#term_hasStatus">im:hasStatus</a></td></tr>
<tr><th>in-domain-of:</th><td><a href="#term_description">dc:description</a> <a href="#term_title">dc:title</a></td></tr></table>

<p>
In order to track an idea's progression throughout a submission, evaluation, and implementation process it is necessary to have states associated with an idea. The <code><a href="#term_Status">im:Status</a></code> class offers this functionality. 
This class contains a set of instances denoting differnet states an <code><a href="#term_CoreIdea">im:CoreIdea</a></code> can be in. 
Examples are <em>new</em>, <em>open</em>, <em>evaluated</em>, <em>implemented</em>, etc.
</p>



<!-- Data properties -->

<div class="specterm" id="term_abstract"/>
---
#### Data Property: im:abstract

<table>

	<tr><th>Domain:</th>
	<td><a href="#term_CoreIdea">im:CoreIdea</a></td></tr>
	<tr><th>Range:</th>
	<td><a href="http://www.w3.org/1999/02/22-rdf-syntax-ns#XMLLiteral" target="rdf">rdf:XMLLiteral</a></td></tr>

</table>
<p>
A medium length abstract describing an <code><a href="#term_CoreIdea">im:CoreIdea</a></code>. For a short title of an idea please use the <code><a href="#term_title">dc:title</a></code> attribute and for a longer description of an idea the <code><a href="#term_description">dc:description</a></code> attribute of an <code><a href="#term_CoreIdea">im:CoreIdea</a></code>.</p>



<div class="specterm" id="term_date"/>
---
#### Data Property: dc:date

<table>

	<tr><th>Domain:</th>
	<td><a href="#term_CoreIdea">im:CoreIdea</a></td></tr>
	<tr><th>Range:</th>
	<td><a href="http://www.w3.org/1999/02/22-rdf-syntax-ns#XMLLiteral" target="rdf">rdf:XMLLiteral</a></td></tr>

</table>
<p>
Time this version of an <code><a href="#term_CoreIdea">im:CoreIdea</a></code> has been created.<br/>
See: <a href="http://purl.org/dc/elements/1.1/date" target="dc">dc:date</a>.</p>


<div class="specterm" id="term_description"/>
---
#### Data Property: dc:description

<table>

	<tr><th>Domain:</th>
	<td><a href="#term_Status">im:Status</a> <a href="#term_CoreIdea">im:CoreIdea</a></td></tr>
	<tr><th>Range:</th>
	<td><a href="http://www.w3.org/1999/02/22-rdf-syntax-ns#XMLLiteral" target="rdf">rdf:XMLLiteral</a></td></tr>

</table>
<p>An account of a <code><a href="#term_Resource">rdf:Resource</a></code>. <code><a href="#term_description">dc:description</a></code> is used in the Idea Ontology to assign a textual 
description to an <code><a href="#term_CoreIdea">im:CoreIdea</a></code> and an<code><a href="#term_Status">im:Status</a></code>.<br/>
See: <a href="http://purl.org/dc/elements/1.1/description" target="dc">dc:description</a>.</p>



<div class="specterm" id="term_title"/>
---
#### Data Property: dc:title

<table>

	<tr><th>Domain:</th>
	<td><a href="#term_CoreIdea">im:CoreIdea</a> <a href="#term_Origin">im:Origin</a> <a href="#term_Status">im:Status</a></td></tr>
	<tr><th>Range:</th>
	<td><a href="http://www.w3.org/1999/02/22-rdf-syntax-ns#XMLLiteral" target="rdf">rdf:XMLLiteral</a></td></tr>

</table>
<p>A name given to the resource. dc:title is used in the Idea Ontology to assign a title to <code><a href="#term_CoreIdea">im:CoreIdea</a></code> and <code><a href="#term_Status">im:Status</a></code>.<br/>
See: <a href="http://purl.org/dc/elements/1.1/title" target="dc">dc:title</a>.</p>



<div class="specterm" id="term_version"/>
---
#### Data Property: im:version

<table>
	<tr><th>Domain:</th>
	<td><a href="#term_CoreIdea">im:CoreIdea</a></td></tr>
	<tr><th>Range:</th>
	<td><a href="http://www.w3.org/1999/02/22-rdf-syntax-ns#XMLLiteral" target="rdf">rdf:XMLLiteral</a></td></tr>

</table>
<p>
Every <code><a href="#term_CoreIdea">im:CoreIdea</a></code> has an <code><a href="#term_version">im:version</a></code> 
number to allow keeping track of different instances of the same idea by means of the <a href="#term_isNewVersionOf">im:isNewVersionOf</a> relationship. 
</p>


<!-- Object properties -->

<div class="specterm" id="term_hasAttachment"/>
---
#### Object Property: im:hasAttachment

<table>
	<tr><th>Domain:</th>
	<td><a href="#term_Resource">rdf:Resource</a></td></tr>
	<tr><th>Range:</th>
	<td><a href="http://xmlns.com/foaf/spec/#term_Document" target="foaf">foaf:document</a></td></tr>

</table>
<p>An <code><a href="#term_CoreIdea">im:CoreIdea</a></code> (more specifically: all <code><a href="#term_Resource">rdf:Resources</a></code>) 
may have documents attached to it (e.g., a screenshot, a process model, technical drawings, etc.) that contains more detailed descriptions of the idea.
</p>



<div class="specterm" id="term_hasCreator"/>
---
#### Object Property: im:hasCreator

<table>
	<tr><th>Domain:</th>
	<td><a href="#term_Resource">rdf:Resource</a></td></tr>
	<tr><th>Range:</th>
	<td><a href="http://xmlns.com/foaf/spec/#term_Person" target="foaf">foaf:Person</a></td></tr>

</table>
<p>Relates a <code><a href="#term_Resource">rdf:Resource</a></code> to its creator 
<code><a href="http://xmlns.com/foaf/spec/#term_Person" target="foaf">foaf:Person</a></code>.
</p>



<div class="specterm" id="term_hasForum"/>
---
#### Object Property: im:hasForum

<table>
	<tr><th>Domain:</th>
	<td><a href="#term_CoreIdea">im:CoreIdea</a></td></tr>
	<tr><th>Range:</th>
	<td><a href="http://rdfs.org/sioc/spec/#term_Forum" target="sioc">sioc:Forum</a></td></tr>

</table>
<p>An <code><a href="#term_CoreIdea">im:CoreIdea</a></code> may have multiple <code><a href="http://rdfs.org/sioc/spec/#term_Forum">
sioc:forums</a></code> associated with it where users are discussing the idea. All <code><a href="http://rdfs.org/sioc/spec/#term_Item">sioc:items</a></code> 
(forum style, blogs, anything) are organized using the <a href="http://rdfs.org/sioc/">SIOC</a> ontology.
</p>


<div class="specterm" id="term_hasRating"/>
---
#### Object Property: im:hasRating

<table>
	<tr><th>Domain:</th>
	<td><a href="#term_Resource">rdf:Resource</a></td></tr>
	<tr><th>Range:</th>
	<td><a href="http://www.tvblob.com/ratings/#Rating">r:Rating</a>
	</td></tr>

</table>
<p>All innovation related <code><a href="#term_Resource">rdf:Resources</a></code> can be rated. If a 
<code><a href="#term_Resource">rdf:Resource</a></code> has a <code><a href="http://www.tvblob.com/ratings/">r:Rating</a></code>, 
this is indicated by <code><a href="#term_hasRating">im:hasRating</a></code>.<br/>
See: <a href="http://www.tvblob.com/ratings/" target="tvblob">tvblob rating</a>.
</p>


<div class="specterm" id="term_hasRealization"/>
---
#### Object Property: im:hasRealization

<table>
	<tr><th>Domain:</th>
	<td><a href="#term_CoreIdea">im:CoreIdea</a></td></tr>
	<tr><th>Range:</th>
	<td><a href="#term_IdeaRealization">im:IdeaRealization</a></td></tr>

</table>
<p>An <code><a href="#term_CoreIdea">im:CoreIdea</a></code> may be, at a later point in the innovation process, be implemented 
in a concrete product or service. This is indicated through a <code><a href="#term_hasRealization">im:hasRealization
</a></code> link to an <code><a href="#term_IdeaRealization">im:IdeaRealization</a></code>.<p>
</p>


<div class="specterm" id="term_hasStatus"/>
---
#### Object Property: im:hasStatus

<table>
	<tr><th>Domain:</th>
	<td><a href="#term_CoreIdea">im:CoreIdea</a></td></tr>
	<tr><th>Range:</th>
	<td><a href="#term_Status">im:Status</a></td></tr>

</table>
<p>Every <code><a href="#term_CoreIdea">im:CoreIdea</a></code> should have an assigned state which 
denots the state of this idea. This could mean that an idea is <em>open, evaluated, implemented,</em> etc.
</p>


<div class="specterm" id="term_hasTagging"/>
---
#### Object Property: im:hasTagging

<table>
	<tr><th>Domain:</th>
	<td><a href="#term_Resource">rdf:Resource</a></td></tr>
	<tr><th>Range:</th>
	<td><a href="http://www.holygoat.co.uk/owl/redwood/0.1/tags/Tagging" target="tags">tags:Tagging</a></td></tr>

</table>
<p>Relates a tag to a <code><a href="#term_Resource">rdf:Resource</a></code>.
</p>


<div class="specterm" id="term_hasTopic"/>
---
#### Object Property: im:hasTopic

<table>
	<tr><th>Domain:</th>
	<td><a href="#term_Resource">rdf:Resource</a></td></tr>
	<tr><th>Range:</th>
	<td><a href="http://www.w3.org/2008/05/skos#Concept" target="skos">skos:Concept</a></td></tr>

</table>
<p>Denots that a given <code><a href="#term_Resource">rdf:Resource</a></code> is related to a 
<code><a href="http://www.w3.org/2008/05/skos#Concept" target="skos">skos:Concept</a></code>.
</p>


<div class="specterm" id="term_isNewVersionOf"/>
---
#### Object Property: im:isNewVersionOf

<table>
	<tr><th>Domain:</th>
	<td><a href="#term_CoreIdea">im:CoreIdea</a></td></tr>
	<tr><th>Range:</th>
	<td><a href="#term_CoreIdea">im:CoreIdea</a></td></tr>

</table>
<p>To account for versioning of ideas and comments different versions of the same idea/comment can be 
linked to each other indicating that they are "the same" but in different versions.
</p>


<div class="specterm" id="term_isSubjectOf"/>
---
#### Object Property: im:isSubjectOf

<table>
	<tr><th>Domain:</th>
	<td><a href="http://www.w3.org/2008/05/skos#Concept">skos:Concept</a></td></tr>
	<tr><th>Range:</th>
	<td><a href="#term_Resource">rdf:Resource</a></td></tr>
	<tr><th>is-inverse-of:</th>
	<td><a href="#term_hasTopic">im:hasTopic</a></td></tr>

</table>
<p>Denotes that the given <code><a href="http://www.w3.org/2008/05/skos#Concept">skos:Concept</a></code> 
is discussed in the related <code><a href="#term_Resource">rdf:Resource</a></code>.
</p>


<div class="specterm" id="term_realizes"/>
---
#### Object Property: im:realizes

<table>
	<tr><th>Domain:</th>
	<td><a href="#term_IdeaRealization">im:IdeaRealization</a></td></tr>
	<tr><th>Range:</th>
	<td><a href="#term_CoreIdea">im:CoreIdea</a></td></tr>
	<tr><th>is-inverse-of:</th>
	<td><a href="#term_hasRealization">im:hasRealization</a></td></tr>
</table>
<p>This <code><a href="#term_IdeaRealization">im:IdeaRealization</a></code> realises (i.e. implements) 
a certain <code><a href="#term_CoreIdea">CoreIdea</a></code>. 
I.e. the product or service realized here, originates/is based on an <code><a href="#term_CoreIdea">CoreIdea</a></code>.
</p>


<!-- end of termlist -->

## Acknowledgments

  <p>This research was funded by the German Federal Ministry of Economics and Technology under the 
  promotional reference 01MQ07012, 01MQ07017, 01MQ07019,  and 01MQ07024 and the German Federal Ministry of Education and Research under grant 
  number 01IA08001A. The responsibility for this publication lies with the authors.</p>

We want to acknowledge in particular the help of Daniel Oberle and Tom Kiemes from the TEXO Project.
	
## Copyright Disclaimer
  
  <p>The information in this document is proprietary to the following THESEUS consortium members funded 
  by means of the German Federal Ministry of Economy and Technology : SAP AG, FZI, Fraunhofer Gesellschaft 
  and Technische Universit&auml;t M&uuml;nchen. The information in this document is provided &#8220;as is&#8221;, 
  and no guarantee or warranty is given that the information is fit for any particular purpose. The above 
  referenced consortium members shall have no liability for damages of any kind including without limitation 
  direct, special, indirect, or consequential damages that may result from the use of these materials subject to 
  any liability which is mandatory due to applicable law. Copyright 2009 by SAP AG, FZI, Fraunhofer Gesellschaft 
  and Technische Universit&auml;t M&uuml;nchen. All rights reserved.</p>


## Recent Changes

Initial version: 2009-11-09
