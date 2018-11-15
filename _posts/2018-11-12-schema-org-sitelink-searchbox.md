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
&lt;script type="application/ld+json"&gt;
{
  "@context": "http://schema.org",
  "@type": "WebSite",
  "url": "http://www.example.com/",
  "potentialAction": {
    "@type": "SearchAction",
    "target": "http://query.example.com/search?q={search_term_string}",
    "query-input": "required name=search_term_string"
  }
}
&lt;/script&gt;
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