---
ID: 117
post_title: Schema.org Sitelink SearchBox
author: iurianu
post_excerpt: ""
layout: post
permalink: >
  http://purls.site/schema-org/schema-org-sitelink-searchbox/
published: true
post_date: 2018-11-12 22:31:32
---
How do we get the Sitelink Searchbox? 

Very simple: we just have to add a small script in the <span>&lt;</span>head<span>&gt;</span> section of our homepage, to tell the Search Engines how the query has to be made, just like in the next example:

<pre>
<span class="pre-tag">&lt;</span>script <span class="pre-attr">type</span>="<span class="pre-value">application/ld+json</span><span class="pre-tag">"&gt;</span>
<span class="pre-tag">{</span>
  "<span class="pre-type">@context</span>": "<span class="pre-value">http://schema.org</span>",
  "<span class="pre-type">@type</span>": "<span class="pre-value">WebSite</span>",
  "<span class="pre-attr">url</span>": "<span class="pre-value">http://www.example.com/</span>",
  "<span class="pre-attr">potentialAction</span>": <span class="pre-tag">{</span>
    "<span class="pre-type">@type</span>": "<span class="pre-value">SearchAction</span>",
    "<span class="pre-attr">target</span>": "<span class="pre-value">http://query.example.com/search?q={search_term_string}</span>",
    "<span class="pre-attr">query-input</span>": "<span class="pre-value">required name=search_term_string</span>"
  <span class="pre-tag">}</span>
<span class="pre-tag">}</span>
<span class="pre-tag">&lt;</span>/script<span class="pre-tag">&gt;</span>
</pre>

So, what do the Search Engines understand from this?

<pre>
    content type:   <span class="pre-value">Website</span>
             url:   <span class="pre-value">http://example.com</span>
          action:   <span class="pre-value">Search</span>
targeted content:   <span class="pre-value"><span class="pre-tag">{</span>search_term_string<span class="pre-tag">}</span></span>
</pre>

...and what do we get from it? Well, we can get something like this:

<a href="http://purls.site/wp-content/uploads/2018/11/lennox-Google-Search1-1.png"><img src="http://purls.site/wp-content/uploads/2018/11/lennox-Google-Search1-1.png" alt="Sitelink Searchbox" width="571" height="332" class="alignnone size-full wp-image-110" /></a>