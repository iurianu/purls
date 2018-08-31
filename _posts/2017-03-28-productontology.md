---
ID: 94
post_title: Productontology Overview
author: iurianu
post_excerpt: ""
layout: post
permalink: >
  https://purls.site/structured-data/productontology/
published: true
post_date: 2017-03-28 15:24:25
---
<p>Productontology is a pseudo-vocabulary used with Wikipedia IDs as classes.</p>
<p>The service provides ca. 300,000 precise definitions for types of product or services that extend the <a href="http://kazenokodomo.tech/ontology/schema-org/" rel="tag">schema.org</a> and <a href="http://kazenokodomo.tech/vocabularies/good-relations/" rel="tag">GoodRelations</a> standards for e-commerce markup.</p>
<p>Schema.org provides a property, additionalType especially created for productontology classes, that can be used for any class defined within its ontology, e.g.:</p>

<pre>
<code>
&lt;div itemscope itemtype="http://schema.org/Product"&gt;
    &lt;link itemprop="<span class="tag-attr">additionalType</span>" href="<span class="tag-attr">http://www.productontology.org/id/Hammer</span>" /&gt;
    &lt;!-- other schema.org properties go in here --&gt;
&lt;/div&gt;
</code>
</pre>
<cite>The example above is taken from the <a rel="tag nofollow" target="_blank" itemprop="isBasedOnUrl" href="http://www.productontology.org">productontology</a> website</cite>

<p>It can also be used with open graphs:</p>

<pre>
<code>
&lt;html version="HTML+RDFa 1.1" xmlns="http://www.w3.org/1999/xhtml" lang="en"
	xmlns:og="http://ogp.me/ns#"
    xmlns:fb="http://www.facebook.com/2008/fbml"
	<span class="tag-attr">xmlns:pto="http://www.productontology.org/id/"&gt;</span>
&lt;head&gt;
    &lt;meta http-equiv="Content-Type" content="application/xhtml+xml; charset=UTF-8"/&gt;
    &lt;title&gt;Example for Facebook Opengraph Protocol on a page describing a(n)/some Hammer&lt;/title&gt;
	&lt;meta property="og:title" content="Example for Facebook Opengraph Protocol on a page describing a(n)/some: Hammer"/&gt;
  	&lt;meta property="og:type" content="<span class="tag-attr">pto:Hammer"</span>/&gt; <span class="tag-comment">/&lt;!-- this is the important line --&gt;</span>
  	&lt;meta property="og:url"content="http://www.uri_for_the_item.com"/&gt; 
  	&lt;meta property="og:image" content="http://www.uri_of_product_image.com/image.png"/&gt; 
  	&lt;meta property="og:site_name" content="Name of Site"/&gt; 
  	&lt;meta property="fb:admins" content="USER_ID"/&gt; 
  	&lt;meta property="og:description" content="long text describing the product"/&gt;
&lt;/head&gt;
&lt;body&gt;
.
.
... the HTML page content..
</code>
</pre>
<cite>The example above is taken from the <a rel="tag nofollow" target="_blank" itemprop="isBasedOnUrl" href="http://www.productontology.org">productontology</a> website</cite>

<h4>How is it used?</h4>

<p>You can use this ontology to describe any object for which a matching entry in the English Wikipedia exists. <br>If you already know the correct URI for the English Wikipedia page, simply cut off the Wikipedia namespace part, e.g.</p>

<p>the Wikipedia URI <em style="color: green;">http://en.wikipedia.org/wiki/<span style="color:red;">Hammer</span></em> will give you <em style="color: green;">http://www.productontology.org/id/<span style="color:red;">Hammer</span></em></p>

<h4>URI Pattern</h4>
<dl>
<dt>Prefix</dt>	<dd><a href="http://prefix.cc/pto" rel="tag nofollow" target="_blank">pto:</a></dd>
<dt>Ontology ID</dt>	<dd>http://www.productontology.org/#</dd>
<dt>Namespace</dt>	<dd>http://www.productontology.org/id/</dd>
</dl>

<h4>Properties</h4>

<p>For describing typical characteristics of the object, like weight, depth, length, width, color, or condition, you can use the predefined GoodRelations properties:</p>

<dl class="property-list">
<dt><a href="http://purl.org/goodrelations/v1#category" rel="tag nofollow" target="_blank">gr:category</a></dt> 
<dd>The name of a category to which this ProductOrService, Offering, BusinessEntity, or Location belongs.</dd>
<dt><a href="http://purl.org/goodrelations/v1#color" rel="tag nofollow" target="_blank">gr:color</a></dt> 
<dd>The color of the product.</dd>
<dt><a href="http://purl.org/goodrelations/v1#condition" rel="tag nofollow" target="_blank">gr:condition</a></dt> 
<dd>A textual description of the condition of the product or service, or the products or services included in the offer (when attached to an Offering)</dd>
<dt><a href="http://purl.org/goodrelations/v1#depth" rel="tag nofollow" target="_blank">gr:depth</a></dt> 
<dd>The depth of the product; typical unit codes: CMT for centimeters, INH for inches</dd>
<dt><a href="http://purl.org/goodrelations/v1#hasEAN_UCC-13" rel="tag nofollow" target="_blank">gr:hasEAN_UCC-13</a></dt> 
<dd>This code is now officially called GTIN-13 (Global Trade Identifier Number) or EAN·UCC-13. Former 12-digit UPC codes can be converted into EAN·UCC-13 code by simply adding a preceeding zero.</dd>
<dt><a href="http://purl.org/goodrelations/v1#hasGTIN-14" rel="tag nofollow" target="_blank">gr:hasGTIN-14</a></dt> 
<dd>The Global Trade Item Number (GTIN-14) of the given ProductOrService or Offering.</dd>
<dt><a href="http://purl.org/goodrelations/v1#hasMPN" rel="tag nofollow" target="_blank">gr:hasMPN</a></dt> 
<dd>The Manufacturer Part Number or MPN is a unique identifier for a product, service, or bundle from the perspective of a particular manufacturer.</dd>
<dt><a href="http://purl.org/goodrelations/v1#hasManufacturer" rel="tag nofollow" target="_blank">gr:hasManufacturer</a></dt> 
<dd>This object property links a ProductOrService to the BusinessEntity that produces it; mostly used with ProductOrServiceModel.</dd>
<dt><a href="http://purl.org/goodrelations/v1#hasStockKeepingUnit" rel="tag nofollow" target="_blank">gr:hasStockKeepingUnit</a></dt> 
<dd>The Stock Keeping Unit, or SKU is a unique identifier for a product, service, or bundle from the perspective of a particular supplier.</dd>
<dt><a href="http://purl.org/goodrelations/v1#height" rel="tag nofollow" target="_blank">gr:height</a></dt> 
<dd>The height of the product. Typical unit codes: CMT for centimeters, INH for inches.</dd>
<dt><a href="http://purl.org/goodrelations/v1#isAccessoryOrSparePartFor" rel="tag nofollow" target="_blank">gr:isAccessoryOrSparePartFor</a></dt> 
<dd>This states that a particular ProductOrService is an accessory or spare part for another product or service.</dd>
<dt><a href="http://purl.org/goodrelations/v1#isConsumableFor" rel="tag nofollow" target="_blank">gr:isConsumableFor</a></dt> 
<dd>This states that a particular ProductOrService is a consumable for another product or service.</dd>
<dt><a href="http://purl.org/goodrelations/v1#isSimilarTo" rel="tag nofollow" target="_blank">gr:isSimilarTo</a></dt> 
<dd>This states that a given ProductOrService is similar to another product or service.</dd>
<dt><a href="http://purl.org/goodrelations/v1#weight" rel="tag nofollow" target="_blank">gr:weight</a></dt> 
<dd>The weight of the ProductOrService; typical unit codes: GRM for gram, KGM for kilogram, LBR for pound.</dd>
<dt><a href="http://purl.org/goodrelations/v1#width" rel="tag nofollow" target="_blank">gr:width</a></dt> 
<dd>The width of the ProductOrService; typical unit codes: CMT for centimeters, INH for inches.</dd>
</dl>
<p>You can also use relevant properties from other GoodRelations-compliant vocabularies, like those for <a href="http://www.heppnetz.de/ontologies/vso/ns" rel="tag nofollow" target="_blank">Vehicles</a> or <a href="http://www.heppnetz.de/ontologies/tio/ns" rel="tag nofollow" target="_blank">Tickets</a>.</p>

<p>When used in combination with http://schema.org/Product, you can also use all standard properties defined for this type, e.g. model or productID.</p>

<h4>External Resources</h4>
<ul>
<li><a href="http://www.productontology.org" rel="tag nofollow" target="_blank">Productontology Website</a></li>
</ul>