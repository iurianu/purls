---
ID: 78
post_title: Microformats Overview
author: iurianu
post_excerpt: ""
layout: post
permalink: >
  https://purls.site/semantic-markup/microformats/microformats-overview/
published: true
post_date: 2017-03-28 12:34:13
---
hAtom is a microformat for identifying semantic information in weblog posts and practically any other place Atom may be used, such as news articles. hAtom content is easily added to most blogs by simple modifications to the blog's template definitions.
<figure><a title="hentry screenshot" href="http://purls.site/wp-content/uploads/2017/03/hentry.png" target="_blank" rel="noopener"><img class="alignnone size-medium wp-image-80" src="http://purls.site/wp-content/uploads/2017/03/hentry.png" alt="" /></a></figure>
&nbsp;

In a hAtom feed, microdata is added by using classes (on HTML elements) or rel attributes (on anchors and links).
The structure of a correctly marked up hAtom is made of:
<ul>
 	<li>class="hfeed" (optional) - declare the presence of hAtom markup</li>
 	<li>class="hentry" (mandatory) - declare the hAtom marked block of content</li>
 	<li>class="entry-title" (mandatory) - the title of the marked document</li>
 	<li>class="entry-content" - the content of the marked document</li>
 	<li>class="entry-summary" - the summary for the content in the document</li>
 	<li>class="published" - the date the document was published</li>
 	<li>class="updated" - the date the document was updated</li>
 	<li>rel="bookmark" - the link for the marked document - used on anchors and links</li>
 	<li>rel="tag" - added on links related to the marked document - used on anchors and links</li>
 	<li>rel="license" - for licensing information - used on anchors and links</li>
 	<li>class="author" - to create the profile of the content's author</li>
</ul>
<p class="note">Time must be written using the <a title="ISO 8601" href="https://en.wikipedia.org/wiki/ISO_8601" target="_blank" rel="nofollow noopener tag">ISO 8601</a> Standard.</p>

<div style="display: none;">hAtom
hentry
adr
bookmark (rel)
tag (rel)
license (rel)
hCard
hCalendar
hReview
xfn
geo
hResume
hRecipe</div>
<h4>Global Resources</h4>
<ul>
 	<li><a href="http://microformats.org/wiki/hatom" target="_blank" rel="nofollow noopener tag">microformats.org Documentation</a></li>
 	<li><a href="https://www.w3.org/wiki/CustomRdfDialects/GrddableMicroformats" target="_blank" rel="nofollow noopener tag">w3.org Documentation</a></li>
 	<li><a href="http://semanticweb.org/wiki/HAtom.html" target="_blank" rel="nofollow noopener tag">Semantic Web Documentation</a></li>
</ul>
<h4>Local Resources</h4>
<p class="related">See our documentation related to the use of <a href="http://purls.site/semantic-markup/" target="_blank" rel="noopener">semantic markup</a></p>