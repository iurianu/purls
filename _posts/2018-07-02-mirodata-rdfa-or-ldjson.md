---
ID: 561
post_title: Microdata, RDFa, or LD+JSON?
author: iurianu
post_excerpt: ""
layout: post
permalink: >
  https://purls.site/structured-data/mirodata-rdfa-or-ldjson/
published: true
post_date: 2018-07-02 16:31:18
---
<figure class="right-thirty"><a href="http://purls.site/wp-content/uploads/2018/06/SEO.jpg"><img src="http://purls.site/wp-content/uploads/2018/06/SEO.jpg" alt="SEO Logo" width="3150" height="3107" class="alignnone size-full wp-image-530" /></a></figure>

When you decide to implement structured data on your website, a very big question comes: "what format to use for implementation?", as most people familiar with structured data know that there are three available formats accepted: RDFa, Microdata, and LD+JSON.

Before making a comparison among these three, I have to specify which are some differences between them:

<h4>RDFa</h4>
RDFa stands for <em>Resource Description Framework in Attributes</em>, and it's a framework derived from RDF, adapted to work with HTML implementation of Structured Data as attributes.
RDFa is a w3.org recommendation.

<h4>Microdata</h4>
Microdata is a set of HTML attributes created for the HTML implementation of Structured Data; in July 2018, it is still a w3.org Note, as no editors were found available to support it.

<h4>LD+JSON</h4>
LD+JSON or JSON-LD stands for <em>Javascript Object Notation for Linked Data</em>. This format, although recommended by Google, does not perfectly map on the HTML content, but only presents some information from the page, in form of triples (quadruples).

<table>
<tbody>
<tr style="font-weight:bold;"> <td>RDFa</td> <td>Microdata</td> <td>LD+JSON</td> </tr>
<tr><td>id</td><td>id</td><td>@id</td></tr>
<tr><td>typeof</td><td>itemtype</td><td>@type</td></tr>
<tr><td>vocab</td><td>-</td><td>@context</td></tr>
<tr><td>-</td><td>itemscope</td><td>-</td></tr>
<tr><td>property</td><td>itemprop</td><td>property</td></tr>
<tr><td>rel</td><td>itemid</td><td>-</td></tr>
<tr><td>rev</td><td>itemref</td><td>-</td></tr>
</tbody>
</table>

<h4>LD+JSON Pros and Cons</h4>

While Google recommended the LD+JSON format for schema.org structured data implementation, more people complained about their website being removed from SERP by Google itself, on the reason that their Structured Data presented information not visible to visitors, even though all info in the script was actually present on the page.

This being said, I, as a Structured Data specialist, recommend using LD+JSON for only some Structured Data, namely the Sitelink SearchBox, the Organization/Person markup, and the BreadcrumbList, all other structured data being marked up as HTML attributes (microdata or RDFa).

<h4>RDFa or Microdata?</h4>

While RDFa is a w3.org recommendation, until this day (July 19, 2018), microdata remained a w3.org note (working draft), as there was no editor to support it.
Even though w3.org didn't adopt the microdata markup language as a recommendation, WHATWG continues to support, and enhance it.

If you try to find out which one of RDFa, and microdata is better for your markup, it won't be easy to find an answer, as they're mostly the same, and it's up to the developer to decide which one he/she will use.

.. to be continued...