---
ID: 92
post_title: The Wonders Around Schema.org
author: iurianu
post_excerpt: ""
layout: post
permalink: >
  http://purls.site/schema-org/the-complete-schema-org-markup/
published: true
post_date: 2018-11-12 21:46:13
---
<a href="http://purls.site/wp-content/uploads/2017/03/schema.org-markup-seo-search.png"><img src="http://purls.site/wp-content/uploads/2017/03/schema.org-markup-seo-search.png" alt="schema.org" width="275" height="183" class="alignnone size-full wp-image-87" /></a>

<h4>Let's start with the beginning:</h4>
<q>Schema.org is a collaborative community activity with a mission to create, maintain, and promote schemas for structured data on the Internet, on web pages, in email messages, and beyond. Webmasters use this shared vocabulary to structure metadata on their websites and to help search engines understand the published content. (<cite><a href="https://en.wikipedia.org/wiki/Schema.org" rel="nofollow tag" title="Wikipedia, the Free Encyclopedia">Wikipedia</a></cite>)</q>

Now that we got its definition, let's understand what it really does.

<h4>Why do we need Schema.org?</h4>
Isn't our website good enough for the Search Engines to be considered important?
Why is there a need for a supplementary code to be added to a website?
Weren't microformats good enough, why create another system?
...and questions could go on.

Well, yes, anyone could ask all these questions before finding what is schema.org, why it was created, and why the Search Engines supported it, and will continue to support it even more.

The Search Engines stated that websites with structured data markup added get a better notability, and are considered more serious than the others.

The implementation can be made in 2 different ways: as HTML attributes (RDFa or microdata), or as a JSON-LD script added in the head, or body of the website.

<h4>What can go wrong with Schema.org?</h4>

Sure, some things can go wrong if the implementation is incorrect, or even incomplete.

In 2017 Google recommended the use of the JSON-LD format wherever possible, with no other explanations; therefore, people (mostly developers) chose this way of implementation as it was way simpler than adding attributes in the HTML content of the webpage. Given this recommendation, the same entity that issued this recommendation (Google) started to give penalties (like complete removal from the SERP) to more websites, stating that the structured data presented information which is not visible to visitors.

Also, since structured data implementation, due to abuse, Google stopped showing Rich Snippets for many categories, but that won't be the case if your structured data is correct, and well implemented.

<h4>How do we stand out in the SERP?</h4>

Here's, in fact, the true meaning of this article, where I tell you what you can get from a perfect implementation of schema.org markup.

<h4>Let's start!!!</h4>

<h5>The Sitelink Searchbox</h5>
The sitelink searchbox is a feature implemented in schema.org, and can be obtained on any website, no matter its size, but with better chances for big websites, with lots of content.
To find more about it, read <a href="http://purls.site/schema-org/schema-org-sitelink-searchbox/" target="_blank">this article</a> on how it's created!

<h5>The SiteNavigationElement</h5>

The SiteNavigationElement is just an extra code (yet quite important) added on the website navigation section. 

Its sole purpose is to present the whole website structure to the Search Engines. It comes mapped on lists (ol, and ul) using the url, and the name of the specific target as points.

Example:

<pre>
    <span class="pre-tag">&lt;ul</span> <span class="pre-attr">itemscope</span> <span class="pre-attr">itemtype</span>="<span class="pre-value">http://schema.org/SiteNavigationElement</span>"<span class="pre-tag">></span>
        <span class="pre-tag">&lt;li</span> <span class="pre-attr">itemprop</span>="<span class="pre-value">name</span>"<span class="pre-tag">></span>
            <span class="pre-tag">&lt;a</span> <span class="pre-attr">itemprop</span>="<span class="pre-value">url</span>" <span class="pre-attr">href</span>="<span class="pre-value">http://example.com/somepage/</span>"<span class="pre-tag">></span>Some Page<span class="pre-tag">&lt;/a></span>
        <span class="pre-tag">&lt;</span><span class="pre-tag">/li</span><span class="pre-tag">></span>
        <span class="pre-tag">&lt;li</span> <span class="pre-attr">itemprop</span>="<span class="pre-value">name</span>"<span class="pre-tag">></span>
            <span class="pre-tag">&lt;a</span> <span class="pre-attr">itemprop</span>="<span class="pre-value">url</span>" <span class="pre-attr">href</span>="<span class="pre-value">http://example.com/otherpage/</span>"<span class="pre-tag">></span>Some Other Page<span class="pre-tag">&lt;/a></span>
        <span class="pre-tag">&lt;/li></span>
    <span class="pre-tag">&lt;/ul></span>
</pre>

<hr>

<h5>The Breadcrumbs</h5>
The breadcrumbs are links to mark the path (in the website) to a specific page, collected in a BreadcrumbList. 
To find more about it, read <a href="http://purls.site/schema-org/schema-org-breadcrumbs/" target="_blank">this article</a> on how it's created!