---
ID: 104
post_title: Social Graphs Overview
author: iurianu
post_excerpt: ""
layout: post
permalink: https://purls.site/seo/social-graphs/
published: true
post_date: 2017-03-29 10:19:37
---
<h2>Make the Shared Snippet Appealing</h2>
<h4>The Use of Meta Tags for The Social Graph</h4>
While many different technologies and schemas exist and could be combined together, there isn't a single technology which provides enough information to richly represent any web page within the social graph. The Open Graph protocol builds on these existing technologies and gives developers one thing to implement.

The Open Graph protocol enables any web page to become a rich object in a social graph. For instance, this is used on Facebook to allow a web page to have the same functionality as any other object on Facebook.
<figure style="border: none;"><a title="Open Graph Shared Snippet" href="http://purls.site/wp-content/uploads/2017/03/shared-snippet.png" target="_blank" rel="noopener"><img class="alignnone size-medium wp-image-108" src="http://purls.site/wp-content/uploads/2017/03/shared-snippet.png" alt="Open Graph Shared Snippet" /></a></figure>
<a href="http://kazenokodomo.tech/social-graphs/open-graphs/">HERE</a> you can find more documentation on open graphs, and <a href="http://kazenokodomo.tech/social-graphs/twitter-cards/">HERE</a> you can find our documentation on Twitter Cards.
<h4><em>The Open Graph Protocol</em></h4>
To turn the web pages into graph objects, some basic metadata must be added to the page.

The initial version of the protocol is based on RDFa which means that additional <em>&lt;meta&gt;</em> tags must be placed in thesection of the web page.

The first to implement the information structuring by the use of this protocol (which is basically an RDF Vocabulary, created for tagging elements on a web page) was Facebook, and now it's used on a large scale, by all Pinterest, Tumblr, Twitter, and other social websites.
<figure style="border: none;"><a title="Shared Snippet on Facebook" href="http://purls.site/wp-content/uploads/2017/03/shared-snippet-after.png" target="_blank" rel="noopener"><img class="alignnone size-medium wp-image-112" src="http://purls.site/wp-content/uploads/2017/03/shared-snippet-after.png" alt="Shared Snippet on Facebook" /></a>The five required properties for every page are:
<em>og:title</em> - The name of your object as it should appear within the graph.
<em>og:type</em> - The type of your object, e.g., "video.movie". Depending on the type you specify, other properties may also be required.
<em>og:image</em> - An image URL which represents your object within the graph.
<em>og:url</em> - The canonical URL of your object that will be used as its permanent ID in the graph.
<em>og:description</em> - A short description of the content to be shared.

If open graph properties are not specified, the default type for any page will be <em>article</em>, the title will be taken from the <em>&lt;title&gt;</em> tag in the <em>&lt;head&gt;</em> section of the web page, the url will be taken from the page's link, the image will be the first image found on the page (even the logo, if there aren't any other images), and the description will be the first textual content on your page (might even be the menu).

Despite a RDF language is used, the Open Graph Protocol is different to other RDF ontologies (like schema.org, SKOS, SIOC, Dublincore etc.), as here, you must use chaining for more details on an object, but this use will be describing in a separate article.

Beside using these 5 required properties, it is highly recommended to <a href="https://developers.facebook.com/docs/apps/register" target="_blank" rel="nofollow noopener">create your own Facebook App ID</a>, so you can customize anything you share.

<section>
<h4>External resources:</h4>
The official website for <a href="http://ogp.me/" target="_blank" rel="nofollow noopener">The Open Graph Protocol</a>

Facebook's documentation for <a href="https://developers.facebook.com/docs/reference/opengraph/" target="_blank" rel="nofollow noopener">The Open Graph Protocol</a>

Google documentation on <a href="https://developers.google.com/web/fundamentals/discovery-and-monetization/social-discovery/" target="_blank" rel="nofollow noopener">Social Discovery</a>

</section>
<h4><em>The Twitter Cards</em></h4>
Twitter Cards are used to attach rich photos, videos and media experience to Tweets that drive traffic to your website. In order to activate this feature, you must add a few lines of HTML to your web page, so users who Tweet links to your content will have a “Card” added to the Tweet that’s visible to all of their followers.

This protocol was not created to share Rich Snippets from your website, but for the Twitter crawlers to consume, and collect the important data about your website content.

There are 4 Card Types:
<em>Summary Card</em> - Title, description, thumbnail, and Twitter account attribution.
<em>Summary Card with Large Image</em> - Similar to a Summary Card, but with a prominently featured image.
<em>App Card</em> - A Card to detail a mobile app with direct download.
<em>Player Card</em> - A Card to provide video/audio/media.

Card properties are simple key-value pairs, each defined in its own HTML meta tag; the combined collection of properties defines the overall card experience on Twitter, and each card supports and requires a specific set of properties.
Only one card per-page is supported. All cards have one basic property in common and that is the card type value.

The only required property, after defining the card <em>type</em>, is <em>site</em>, and, if you use the Open Graph Protocol, you must not add twitter tags that create duplicate content, as the content from the open graph will be used; therefore, a collection of data on a web page could look like this:
&lt;meta <em>name="twitter:card"</em> content="summary" /&gt;
&lt;meta <em>name="twitter:site"</em> content="@kazenokodomo_ro" /&gt;
&lt;meta <em>name="twitter:creator"</em> content="@iurianu" /&gt;
&lt;meta <em>property="og:url"</em> content="http://kazenokodomo.tech" /&gt;
&lt;meta <em>property="og:title"</em> content="A Website for Semantic SEO" /&gt;
&lt;meta <em>property="og:description"</em> content="When you notice that the old SEO techniques don't work anymore, and your website is losing space, you must wonder why did that happen; the answer is that, starting in 2014, Google introduced the Structured Data." /&gt;
&lt;meta <em>property="og:image"</em> content="http://kazenokodomo.website/wp-content/uploads/2016/03/knk-logo.png" /&gt;

Twitter Cards generated from developer meta tags only appear when a Tweet is either expanded in the timeline (on web) or viewed on the Tweet’s individual permalink page (by clicking on the date from the timeline, either on web or on mobile).
In limited circumstances, Cards may appear in the timeline, such as in images posted to Twitter, Ad formats and Twitter-run experiments.

<section>
<h4>External resources:</h4>
Twitter's documentation on <a href="https://dev.twitter.com/cards/overview" target="_blank" rel="nofollow noopener">Twitter Cards</a>

Google documentation on <a href="https://developers.google.com/web/fundamentals/discovery-and-monetization/social-discovery/" target="_blank" rel="nofollow noopener">Social Discovery</a>

</section></figure>