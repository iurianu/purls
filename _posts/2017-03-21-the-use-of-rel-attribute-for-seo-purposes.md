---
ID: 356
post_title: 'The use of &#8216;rel&#8217; attribute for SEO purposes'
author: iurianu
post_excerpt: ""
layout: post
permalink: >
  https://purls.site/semantic-markup/the-use-of-rel-attribute-for-seo-purposes/
published: true
post_date: 2017-03-21 10:37:51
---
In HTML pages, the links can be used to indicate the relationship between documents, where they can be set to point to related sources by using an &lt;a&gt;, &lt;area&gt;, or &lt;link&gt; element.

Beside the notorious link rel="stylesheet" used to point to CSS files used to add styles to HTML elements, HTML makes use of lots of other <em>rel</em> values, that can enhance your online presence, if correctly used.
First of all, in the &lt;head&gt; section of the file, you must use <em>rel="canonical"</em> on a link to specify the canonical URL for the current document, in order to avoid duplicate content.

In the same series, <em>rel="alternate</em>" designates alternative versions of the document. If used with the <em>lang</em> attribute, it will be used to point to a translated version, and if used with the media attribute, it will link to a version designed for a different medium (or media).

Very important for SEO is the use of <em>rel="profile"</em> to link your Google Plus Profile, so Google will know exactly what he is looking at.

Although the links in the &lt;head&gt; section are of vital importance, in regards of SEO, the links in the page content can be successfully used in creating your online profile.

<figure><a href="http://purls.site/wp-content/uploads/2018/06/rel-attributes-img.png"><img src="http://purls.site/wp-content/uploads/2018/06/rel-attributes-img.png" alt="Rel Attributes" width="733" height="400" class="alignnone size-full wp-image-360" /></a></figure>

HTML5 provides an extensive list of <em>rel</em> uses, but the most important are the ones that define your content and profile as an entity.
<h4>Nofollow</h4>
The value <em>nofollow </em>for the rel tag indicates that the destination of that hyperlink should not be given any additional weight or ranking by the search engines performing the link analysis.
<h4>Tag</h4>
By adding <em>rel="tag"</em> to a hyperlink, a page indicates that the destination is a keyword or subject for the current page. Note that a tag may just refer to a major portion of the current page.
<h4>Bookmark</h4>
The anchor with <em>rel="bookmark"</em> refers to a link of a key entry point within a document. This is to be added on all anchors within the page content that link to materials used. It can be successfully used with <em>itemprop="isBasedOnUrl"</em>, in schema.org markup. The title attribute may be used, for example, to label the bookmark. Note that several bookmarks may be defined in each document.
<h4>Me</h4>
By using<em> rel="me"</em>, you indicate that the referenced target represents a profile for the same person as does the current document. This rel value will be used with the schema.org value<em> itemprop="url"</em>.
<h4>Publisher</h4>
The value of <em>rel="publisher"</em> indicates that the referenced target is a metadata profile (i.e. a social-media profile such as a Facebook, or a Google Plus profile) for the publisher of the current page, or some portion of the current page. This rel value can be used together with the <em>itemprop="sameAs"</em>.
<h4>Copyright</h4>
The value of <em>rel="copyright"</em> will be used to refer to a copyright statement for the current document. It can be used with the schema.org markup for CreativeWork, with <em>itemprop="copyrightHolder"</em>[Person or Organization] and <em>itemprop="copyrightYear"</em> (to use use a time note).

If you think these values are not enough to perfectly represent your content or your person/organization, you can check the extensive list of approved <em>rel</em> values on <a class="alternate-url" href="http://microformats.org/wiki/existing-rel-values" target="_blank" rel="noopener">microformats.org</a>