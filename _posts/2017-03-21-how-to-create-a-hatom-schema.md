---
ID: 79
post_title: How to create a hAtom Schema
author: iurianu
post_excerpt: ""
layout: post
permalink: >
  http://purls.site/microformats/how-to-create-a-hatom-schema/
published: true
post_date: 2017-03-21 20:56:22
---
<h4>Typical microformats for webpages</h4>

<figure><a href="http://purls.site/wp-content/uploads/2017/03/hentry.png"><img src="http://purls.site/wp-content/uploads/2017/03/hentry.png" alt="hentry" width="612" height="320" class="alignnone size-full wp-image-81" /></a></figure>

The typical microdata for a page needs only a few elements marked up; therefore, when you start marking up your page, these are the main marks you can use:
<ol class="pointed">
<li>add class "hfeed" on the main container of your content, to let the crawler know there is a hAtom markup (optional);</li>
<li>add class "hentry" on the containing block element in your content;</li>
<li>add class="entry-title" on your H1 (this is the name of the work);</li>
<li>add class="entry-content" on the block element surrounding your page's content;</li>
<li>add class="entry-summary" on the summary of your content;</li>
<li>add rel="bookmark" on the anchor of the marked up page;</li>
<li>add rel="tag" on the links and anchors use to tag your content;</li>
<li>add class="published" on the publishing date.</li>
</ol>
<p class="note">Note: usually add class="hfeed" on HTML tag, and class="hentry" on BODY tag.</p>

Here you can see a page marked up with the essential microdata for a hFeed:

<pre>
&lt;html class="<span class="tag-attr">hfeed</span>"&gt;
  &lt;body class="<span class="tag-attr">hentry</span>"&gt;
    &lt;h1 class="<span class="tag-attr">entry-title</span>"&gt;hAtom Example&lt;/h1&gt;
    &lt;main class="<span class="tag-attr">entry-content</span>"&gt;
      &lt;p&gt;This is a hAtom micordata example created for study puroposes only.&lt;/p&gt;
      &lt;section class="<span class="tag-attr">entry-summary</span>"&gt;
        Created for: &lt;a rel="<span class="tag-attr">tag</span>" <span class="tag-attr">href</span>="http://purls.site"&gt;PURLS&lt;/a&gt;.   
        Article link: &lt;a rel="<span class="tag-attr">bookmark</span>" <span class="tag-attr">href</span>="http://purls.site/semantic-markup/how-to-create-a-hatom-schema/"&gt;here&lt;/a&gt;.
        Published on: &lt;time class="<span class="tag-attr">published</span>" <span class="tag-attr">datetime</span>="2016-04-25"&gt;April 25, 2016&lt;/time&gt;
        Updated on: &lt;time class="<span class="tag-attr">updated</span>" <span class="tag-attr">datetime</span>="2018-06-07"&gt;June 7, 2018&lt;/time&gt;
      &lt;/section&gt;
      &lt;section class="<span class="tag-attr">author vcard</span>"&gt;
        &lt;p&gt;Author: &lt;br /&gt;
          &lt;span class="<span class="tag-attr">fn n</span>"&gt;
          &lt;span class="<span class="tag-attr">given-name</span>"&gt;Iulian&lt;/span&gt;
          &lt;span class="<span class="tag-attr">family-name</span>"&gt;Andriescu&lt;/span&gt;
          &lt;/span&gt;        
        &lt;/p&gt;
        &lt;address class="<span class="tag-attr">adr</span>"&gt;
          Address:&lt;br /&gt;
          &lt;p&gt;
            &lt;span class="<span class="tag-attr">street-address</span>"&gt;93 Vasile Lupu Str.&lt;/span&gt;, 
            &lt;span class="<span class="tag-attr">postal-code</span>"&gt;700319&lt;/span&gt;, 
            &lt;span class="<span class="tag-attr">locality</span>"&gt;Iaşi&lt;/span&gt;, 
            &lt;span class="<span class="tag-attr">region</span>"&gt;Iaşi&lt;/span&gt;, 
            &lt;span class="<span class="tag-attr">country-name</span>"&gt;România&lt;/span&gt;
          &lt;/p&gt;
        &lt;/address&gt;
        &lt;p&gt;Organization: 
          &lt;span class="<span class="tag-attr">org</span>"&gt;kazenokodomo&lt;/span&gt;        
        &lt;/p&gt;
      &lt;/section&gt;
    &lt;/main&gt;
  &lt;/body&gt;
&lt;/html&gt;
</pre>

Click <a rel="alternate" target="_blank" href="http://purls.site/cdn/hatom-example.html">here</a> to see the Page this markup is taken from!
You can see how Google reads the markup on this page <a href="https://search.google.com/structured-data/testing-tool/u/0/#url=http%3A%2F%2Fpurls.site%2Fcdn%2Fhatom-example.html" target="_blank">here</a>.