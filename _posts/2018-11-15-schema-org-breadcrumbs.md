---
ID: 141
post_title: Schema.org Breadcrumbs
author: iurianu
post_excerpt: ""
layout: post
permalink: >
  http://purls.site/schema-org/schema-org-breadcrumbs/
published: true
post_date: 2018-11-15 22:12:52
---
The breadcrumbs are actually links to mark the path (in the website) to a specific page, collected in a BreadcrumbList. 
The creation of a Breadcrumblists is very simple, this being, in fact, a list of Webpages defined as points, and the <a target="_blank" href="https://schema.org/BreadcrumbList" rel="nofollow">schema.org documentation on breadcrumbs</a> presents very good examples.
The result of this implementation will be the change of the link in the Rich Snippet to a list that presents the path for the page.

<figure><a title="Breadcrumbs" href="http://purls.site/wp-content/uploads/2018/11/Breadcrumbs.png"><img src="http://purls.site/wp-content/uploads/2018/11/Breadcrumbs.png" alt="Breadcrumbs" width="525" height="93" class="alignnone size-full wp-image-139" /></a></figure>

A simple code for a BreadcumbList looks like the one in the following example, and the recommended number of nodes is between 3, and 5, because the last node won't be shown in the breadcrumb list from the rich snippet.

<pre>
<span class="pre-tag"><</span><span class="pre-tag">script</span> <span class="pre-attr">type</span>="<span class="pre-value">application/ld+json</span>"<span class="pre-tag">></span>
<span class="pre-tag">{</span>
 "<span class="pre-type">@context</span>": "<span class="pre-value">http://schema.org</span>",
 "<span class="pre-type">@type</span>": "<span class="pre-value">BreadcrumbList</span>",
 "<span class="pre-attr">itemListElement</span>":<span class="pre-tag">[</span>
  <span class="pre-tag">{</span>
   "<span class="pre-type">@type</span>": "<span class="pre-value">ListItem",
   "<span class="pre-attr">position</span>": <span class="pre-value">1</span>,
   "<span class="pre-attr">item</span>":<span class="pre-tag">{</span>
    "<span class="pre-type">@id</span>": "<span class="pre-value">http://purls.site</span>",
    "<span class="pre-attr">name</span>": "<span class="pre-value">SD Master</span>"
    <span class="pre-tag">}</span>
  <span class="pre-tag">}</span>,
  <span class="pre-tag">{</span>
   "<span class="pre-type">@type</span>": "<span class="pre-value">ListItem</span>",
   "<span class="pre-attr">position</span>": <span class="pre-value">2</span>,
   "<span class="pre-attr">item</span>":<span class="pre-tag">{</span>
     "<span class="pre-type">@id</span>": "<span class="pre-value">http://purls.site/Blog</span>",
     "<span class="pre-attr">name</span>": "<span class="pre-value">Blog</span>"
   <span class="pre-tag">}</span>
  <span class="pre-tag">}</span>
 <span class="pre-tag">]</span>
<span class="pre-tag">}</span>
<span class="pre-tag"><</span><span class="pre-tag">/script</span><span class="pre-tag">></span>
</pre>