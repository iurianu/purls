---
ID: 165
post_title: Schema.org SiteNavigationElement
author: iurianu
post_excerpt: ""
layout: post
permalink: >
  http://purls.site/schema-org/schema-org-sitenavigationelement/
published: true
post_date: 2018-11-26 08:17:17
---
The SiteNavigationElement is just an extra code (yet quite important) added on the website navigation section. 
<figure class="figure-50"><a href="http://purls.site/wp-content/uploads/2017/03/schema.org-markup-seo-search.png"><img src="http://purls.site/wp-content/uploads/2017/03/schema.org-markup-seo-search.png" alt="schema.org" width="275" height="183" class="alignnone size-full wp-image-87" /></a></figure>

Its sole purpose is to present the whole website structure to the Search Engines. It comes mapped on the menu lists (ol, and ul) using the url, and the name of the specific target as points.

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