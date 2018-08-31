---
ID: 61
post_title: Microdata Overview
author: iurianu
post_excerpt: ""
layout: post
permalink: >
  https://purls.site/structured-data/microdata-page/
published: true
post_date: 2017-03-28 12:15:01
---
<section id="microdata" class="article-section">
<p class="citation"><q>Microdata is a WHATWG HTML specification used to nest metadata within existing content on web pages.
Search engines, web crawlers, and browsers can extract and process Microdata from a web page and use it to provide a richer browsing experience for users.
Search engines benefit greatly from direct access to this <em>structured data</em> because it allows search engines to understand the information on web pages and provide more relevant results to users.
Microdata uses a supporting vocabulary to describe an <em>item</em> and <em>name-value pairs</em> to assign values to its <em>properties</em>.
Microdata is an attempt to provide a simpler way of annotating HTML elements with machine-readable tags than the similar approaches of using RDFa and microformats.</q>
<cite style="float: right;">(from Wikipedia, the Free Encyclopedia).</cite></p>

<figure class="article-image"><a class="url" href="http://purls.site/wp-content/uploads/2017/03/microdata-image.jpg" target="_blank" rel="image noopener"><img src="http://purls.site/wp-content/uploads/2017/03/microdata-image.jpg" alt="Microdata Image" /></a></figure>
</section><section id="microdata" class="article-section">
<h4>How does microdata work?</h4>
Creating a block of information defined with microdata is just like creating a function in OOP:
<ul>
 	<li>you define a scope and a type for your block of content, by using the predefined attributes <em>itemscope</em> and <em>itemtype</em>;</li>
 	<li>you define properties for the elements inside your block of content, using the attribute <em>itemprop</em></li>
 	<li>you can use an <em>itemref</em> attribute, to link a block of content with a <em>scope</em> and <em>type</em> to another block of content that it refers to, and has a particular <em>ID</em>;</li>
 	<li>you can use the <em>itemid</em> attribute to indicate an unique identifier for more items.</li>
</ul>
</section><section id="itemscope" class="article-section">
<h4>itemscope</h4>
The <em>itemscope</em> attribute is to be used on every block of content on which we must define a new <em>type</em>.
New <em>types</em> defined without an <em>itemscope</em> are skipped by the microdata parser, and the <em>properties</em> of the elements inside the block of content will become <em>properties</em> of the closest parent block of content that has both <em>itemscope</em> and <em>itemtype</em> defined.

Itemscope has no defined value, and it will be declared with an empty value (<em>itemscope</em>), getting a boolean value of <em>true</em> or as an attribute="value" pair, declared as <em>itemscope="itemscope"</em> (for XHTML).

There are two ways of declaring a new <em>scope</em> on some content in the page:

1. Defining a block of content as a particular type, separated of the rest of content in the page;
This can be made by using the <em>itemscope</em> and <em>itemtype</em> attributes only, on the main(parent) html block.

Note: Even if <em>itemscope</em> and <em>itemtype</em> are defined on an html block element, there must be at least one element defined as a property (<em>itemprop</em>) for that block, in order for this to be considered by the microdata parser.
<pre><code>
... some HTML content with defined scope and type
&lt;/div&gt;
&lt;blockquote <span class="tag-attr">itemscope</span> <span class="tag-attr">itemtype="https://schema.org/Person"</span>&gt;
  &lt;span <span class="tag-attr">itemprop="name"</span>&gt;Person Name&lt;/span&gt;
  
  ... other information
  
&lt;/blockquote&gt;
&lt;div&gt;
... some HTML content tied to the one before the blockquote
</code></pre>
2. Defining a new type on a block of content, as a <em>property</em> for the parent block with defined scope and type
In order to tie the content inside our HTML block to the content of the parent block, we must use all <em>itemprop</em>, <em>itemscope</em>, and <em>itemtype</em> on our element.
<pre><code>
... some HTML content with defined scope and type
&lt;/div&gt;
&lt;blockquote <span class="tag-attr">itemprop="author"</span> <span class="tag-attr">itemscope</span> <span class="tag-attr">itemtype="https://schema.org/Person"</span>&gt;
  &lt;span <span class="tag-attr">itemprop="name"</span>&gt;Author Name&lt;/span&gt;
  
  ... other information
  
&lt;/blockquote&gt;
&lt;div&gt;
... some more HTML content tied to the one before the blockquote
</code></pre>
</section><section id="itemtype" class="article-section">
<h4>itemtype</h4>
The <em>itemtype</em> attribute is the one that tells the microdata parser what kind of content you have in an HTML block of content. It can be used on both block or inline HTML elements, and is ignored by the parser unless it has an <em>itemscope</em> declared.

The default value of an itemtype will be an URL of an existing vocabulary (e.g. <em>itemtype="https://schema.org/CreativeWork"</em> or <em>itemtype="http://mysite.com/ontologies/my-vocabulary.owl"</em>)

</section><section id="itemprop" class="article-section">
<h4>itemprop</h4>
The <em>itemprop</em> attributes are used on HTML (block or inline) elements to tell the microdata parser what kind of content lies inside that element, and how is it connected to the content of the closest parent block of content with a <em>scope</em> and <em>type</em> defined. These <em>properties</em> are custom for each <em>types</em>, and can only be used on those they have been created for.

The values for <em>itemprop</em> will be the content between the opening, and the closing tags, for all the block elements, and for some of the inline elements; therefore, the next example will be read: <em>name : John Doe</em>
<pre><code>
&lt;span itemprop="<span class="tag-attr">name</span>"&gt;<span class="tag-attr">John Doe</span>&lt;/span&gt;
</code></pre>
For anchors (<em>a</em>) and <em>links</em>, the value of the property will be given by the value of the href attribute; both of the next examples will be read as <em>url : "http://example.com"</em>:
<pre><code>
&lt;a itemprop="<span class="tag-attr">url</span>" href="<span class="tag-attr">http://example.com</span>" title="Example Website"&gt;Example Website&lt;/a&gt;

&lt;link itemprop="<span class="tag-attr">url</span>" href="<span class="tag-attr">http://example.com</span>" title="Example Website" /&gt;
</code></pre>
On meta tags, the value of the <em>property</em> will be defined by using the <em>content</em> attribute; the next example will be read <em>name : John Doe</em>:
<pre><code>
&lt;meta itemprop="<span class="tag-attr">name</span>" <span class="tag-attr">content</span>="John Doe" / &gt;
</code></pre>
When using the <em>time</em> tag to define dates, a <em>datetime</em> attribute must be used; if this one is not present, the read value will be the one between the opening and closing tags; the next example will be read <em>datePublished : 2016-05-16</em>.
<pre><code>
&lt;time itemprop="<span class="tag-attr">datePublished</span>" <span class="tag-attr">datetime</span>="2016-05-16"&gt;<span class="tag-attr">May 16, 2016</span>&lt;/time&gt;
</code></pre>
On image, iframe, embed, map, and area, the value of the <em>property</em> will be given by the value of the <em>source</em> attribute (src); the next example will be read <em>image : http://example.com/image.jpg</em>:
<pre><code>
&lt;img itemprop="<span class="tag-attr">image</span>" <span class="tag-attr">src</span>="http://example.com/image.jpg" / &gt;
</code></pre>
The <em>object</em>'s value as the microdata <em>property</em> will be given by the <em>data</em> attribute; the next example will be read as <em>embedUrl : helloworld.swf</em>:
<pre><code>
&lt;object itemprop="<span class="tag-attr">embedUrl</span>" width="400" height="400" <span class="tag-attr">data</span>="helloworld.swf"&gt;&lt;/object&gt;
</code></pre>
</section><section id="itemref" class="article-section">
<h4>itemref</h4>
Items can use non-descendant properties (name-value pairs that aren't children of the our element) via the attribute <em>itemref</em>. This attribute is used to connect the IDs of properties for items in other places (on the same page).
The next example defines the properties <em>url</em>, and <em>name</em>. Additionally, it references the ID <em>band-members</em>, which contains the item <em>members</em> with four name properties, each of which have a different value.
<pre><code>
&lt;p itemscope itemtype="https://schema.org/MusicGroup" <span class="tag-attr">itemref="band-members"</span>&gt;
  I’m going to the
  &lt;a itemprop="url" href="http://www.saltercane.com/"&gt;
  &lt;span itemprop="name"&gt;Salter Cane&lt;/span&gt;&lt;/a&gt; gig next week. Excited!&lt;/p&gt;
  .
  .
  .
  &lt;p&gt;Salter Cane are &lt;span <span class="tag-attr">id="band-members"</span>
  itemprop="members" itemscope itemtype="https://schema.org/Person"&gt;
  &lt;span itemprop="name"&gt;Chris Askew&lt;/span&gt;, 
  &lt;span itemprop="name"&gt;Jeremy Keith&lt;/span&gt;, 
  &lt;span itemprop="name"&gt;Jessica Spengler&lt;/span&gt;
  and &lt;span itemprop="name"&gt;Jamie Freeman&lt;/span&gt;.&lt;/span&gt;&lt;/p&gt;
</code></pre>
<cite>The example above is taken from the <a href="http://html5doctor.com/microdata/" target="_blank" rel="nofollow noopener tag">html5doctor website</a></cite>

</section><section id="itemid" class="article-section">
<h4>itemid</h4>
The <em>itemid</em> attribute is used as a global identifier for items. Sometimes, an item gives information about a topic that has a global identifier.
For example, books can be identified by their ISBN number.
Vocabularies (as identified by the <em>itemtype</em> attribute) can be designed such that <em>items</em> get associated with their global identifier in an unambiguous way by expressing them as URLs given in an <em>itemid</em> attribute.
Here, an item is talking about a particular book:
<pre><code>
&lt;dl itemscope
    itemtype="http://vocab.example.net/book"
    <span class="tag-attr">itemid="urn:isbn:0-330-34032-8"</span>&gt;
 &lt;dt&gt;Title
 &lt;dd itemprop="title"&gt;The Reality Dysfunction
 &lt;dt&gt;Author
 &lt;dd itemprop="author"&gt;Peter F. Hamilton
 &lt;dt&gt;Publication date
 &lt;dd&gt;&lt;time itemprop="pubdate" datetime="1996-01-26"&gt;26 January 1996&lt;/time&gt;
&lt;/dl&gt;
</code></pre>
<cite>The example above is taken from the <a href="https://www.w3.org/TR/2013/NOTE-microdata-20131029/#attr-itemid" target="_blank" rel="nofollow noopener tag">w3.org website</a></cite>

The exact meaning of the URLs given in <em>itemid</em> attributes depends on the vocabulary used: the <em>"http://vocab.example.net/book"</em> vocabulary in this example would define that the <em>itemid</em> attribute takes a <em>urn</em>: URL pointing to the ISBN of the book.

As another use, by re-using the same <em>itemid</em>, you can tell the microdata parser that you're talking about the same item in different parts of the page.
The <em>itemid</em> attribute must not be specified on elements that do not have both an <em>itemscope</em> attribute and an <em>itemtype</em> attribute specified, and must not be specified on elements with an <em>itemscope</em> attribute whose <em>itemtype</em> attribute specifies a vocabulary that does not support global identifiers for items, as defined by that vocabulary's specification.
<pre><code>
&lt;blockquote class="name"&gt;
  &lt;div itemscope itemtype="http://www.schema.org/Product" <span class="tag-attr">itemid="Product1"</span>&gt;
    &lt;span <span class="tag-attr">itemprop="name"</span>&gt;Product Name #1&lt;/span&gt;
  &lt;/div&gt;
  &lt;div itemscope itemtype="http://www.schema.org/Product" <span class="tag-attr">itemid="Product2"</span>&gt;
    &lt;span <span class="tag-attr">itemprop="name"</span>&gt;Product Name #2&lt;/span&gt;
  &lt;/div&gt;
&lt;/blockquote&gt;
&lt;blockquote class="price"&gt;
  &lt;div itemscope itemtype="http://www.schema.org/Product" <span class="tag-attr">itemid="Product1"</span>&gt;
    &lt;em itemprop="offers" itemscope itemtype="http://schema.org/Offer"&gt;
      &lt;span <span class="tag-attr">itemprop="price"</span>&gt;Product Price #1&lt;/span&gt;
    &lt;/em&gt;
  &lt;/div&gt;
  &lt;div itemscope itemtype="http://www.schema.org/Product" <span class="tag-attr">itemid="Product2"</span>&gt;
    &lt;em itemprop="offers" itemscope itemtype="http://schema.org/Offer"&gt;
      &lt;span <span class="tag-attr">itemprop="price"</span>&gt;Product Price #2&lt;/span&gt;
    &lt;/em&gt;
  &lt;/div&gt;
&lt;/blockquote&gt;
</code></pre>
<cite>The example above is inspired by an example on <a href="http://stackoverflow.com/questions/11109669/microdata-itemid-to-identify-elements-scattered-throughout-an-html-doc-html-tabl" target="_blank" rel="nofollow noopener tag">stackoverflow</a></cite>

</section><section id="externalResources" class="article-section">
<h4>External references:</h4>
<ul>
 	<li><a href="https://html.spec.whatwg.org/multipage/microdata.html#microdata" rel="tag nofollow">WHATWG Documentation on microdata</a></li>
 	<li><a href="https://en.wikipedia.org/wiki/Microdata_(HTML)" rel="tag nofollow">Wikipedia Page on microdata</a></li>
 	<li><a href="http://html5doctor.com/microdata/" rel="tag nofollow">HTML5Doctor Page on microdata</a></li>
</ul>
</section>