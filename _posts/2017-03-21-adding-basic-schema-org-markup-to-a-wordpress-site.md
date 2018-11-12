---
ID: 63
post_title: >
  Adding Basic Schema.org Markup to a
  WordPress Site
author: iurianu
post_excerpt: ""
layout: post
permalink: >
  http://purls.site/schema-org/adding-basic-schema-org-markup-to-a-wordpress-site/
published: true
post_date: 2017-03-21 20:28:12
---
<section>This article is meant to give all the information to add the minimal schema.org structured data required for your wordpress website.
I will first explain how to modify your theme's templates, without touching the design.
<h4>The Recommended Website Markup</h4>
Before starting using this tutorial, I advice you install <a href="https://yoast.com/wordpress/plugins/seo/" target="_blank" rel="nofollow noopener">Yoast SEO Plugin</a>, and configure it to show the <a href="http://schema.org/WebSite" target="_blank" rel="nofollow noopener">http://schema.org/WebSite</a> markup on your Home Page. If you don't want to use this plugin (or other plugin that adds this markup), you must go to <em>header.php</em> and add the following script:
<pre>&lt;?php if (is_home() || is_front_page()) { ?&gt;
&lt;script type='application/ld+json'&gt;
{"@context":"http://schema.org/", "@type":"WebSite", "@id":"#website",
"url":"&lt;?php echo get_site_url(); ?&gt;", "name":"&lt;?php echo get_bloginfo('name'); ?&gt;",
"potentialAction":{"@type":"SearchAction","target":"&lt;?php echo get_site_url(); ?&gt;"/?s={search_term_string}",
"query-input":"required name=search_term_string"}}
&lt;/script&gt;
&lt;?php } ?&gt;
</pre>
<p class="note">This script will create the content required for this markup using the information on your website; you can copy it right from the above, and paste it into your <em>header.php</em> file.</p>
Maybe you're wondering what this markup does, and what is it used for; well, it allows the search engines to create sitelinks foryour pages, so your results in the SERP (Search Engine Results Page) will look like in this picture.
<figure><a href="http://purls.site/wp-content/uploads/2018/06/sitelinks.png"><img class="alignnone size-full wp-image-330" src="http://purls.site/wp-content/uploads/2018/06/sitelinks.png" alt="Sitelinks" width="601" height="181" /></a></figure>
</section>&nbsp;

<section>
<h4>Defining the Webpage type for each page on your website</h4>
In the same file, <em>header.php</em>, you should find the next line:
<pre>&lt;html &lt;?php language_attributes(); ?&gt;&gt;
</pre>
Let's first set the type for your Home Page. This one is tricky, because you can have either a static page, or a page showing your latest posts. So. to fix this, we must use some more conditions:
<pre>&lt;?php if (is_home() || is_front_page() ) { ?&gt;
	&lt;?php if (!is_single()) { ?&gt;
&lt;html &lt;?php language_attributes(); ?&gt; itemscope="itemscope" itemtype="http://schema.org/Blog"&gt;
	&lt;?php } else { ?&gt;
&lt;html &lt;?php language_attributes(); ?&gt; itemscope="itemscope" itemtype="http://schema.org/Webpage"&gt;
        &lt;?php } ?&gt;
&lt;?php } ?&gt;
</pre>
The next step is adding the WebPage Type for all other pages on your website. So we're going to add different types for <a href="https://schema.org/SearchResultsPage" target="_blank" rel="nofollow noopener">Search Results Page</a>, <a href="https://schema.org/ContactPage" target="_blank" rel="nofollow noopener">Contact Page</a>, <a href="https://schema.org/AboutPage" target="_blank" rel="nofollow noopener">About Page</a>, <a href="https://schema.org/ProfilePage" target="_blank" rel="nofollow noopener">Profile Page</a>, <a href="https://schema.org/QAPage" target="_blank" rel="nofollow noopener">FAQ Page</a>, <a href="https://schema.org/Blog" target="_blank" rel="nofollow noopener">Blog</a>, and <a href="https://schema.org/BlogPosting" target="_blank" rel="nofollow noopener">Blog Posts</a>. We're also going to add a simple <a href="https://schema.org/WebPage" target="_blank" rel="nofollow noopener">WebPage</a> type for all other pages which don't comply to the rules above.
After adding all these types, your code should look like this:
<pre>&lt;?php <span class="pre-val">if</span> (is_home() <span class="pre-val">||</span> is_front_page() )?&gt;
	&lt;?php <span class="pre-val">if</span> (<span class="pre-val">!</span>is_single()) { ?&gt;
		&lt;html &lt;?php language_attributes(); ?&gt; itemscope="itemscope" itemtype="http://schema.org/Blog"&gt;
	&lt;?php } <span class="pre-val">else</span> { ?&gt;
		&lt;html &lt;?php language_attributes(); ?&gt; itemscope="itemscope" itemtype="http://schema.org/Webpage"&gt;
	&lt;?php } ?&gt;
&lt;?php } <span class="pre-val">elseif</span> ( <span class="pre-val">!</span>is_single() <span class="pre-val">&amp;&amp; !</span>is_page() <span class="pre-val">&amp;&amp; !</span>is_search() ) { ?&gt;
	&lt;html &lt;?php language_attributes(); ?&gt; itemscope="itemscope" itemtype="http://schema.org/Blog"&gt;
&lt;?php } <span class="pre-val">elseif</span> ( is_single() <span class="pre-val">&amp;&amp; !</span>is_search() <span class="pre-val">&amp;&amp; !</span>is_page_template('archive.php')) {?&gt;
	&lt;html &lt;?php language_attributes(); ?&gt; itemscope="itemscope" itemtype="http://schema.org/BlogPosting"&gt;
&lt;?php } <span class="pre-val">elseif</span> ( is_search() <span class="pre-val">||</span> is_page_template('archive.php') ) { ?&gt;
	&lt;html &lt;?php language_attributes(); ?&gt; itemscope="itemscope" itemtype="http://schema.org/SearchResultsPage"&gt;
&lt;?php } <span class="pre-val">elseif</span> ( is_page('contact-us') <span class="pre-val">||</span> is_page('contact') ) { ?&gt;
	&lt;html &lt;?php language_attributes(); ?&gt; itemscope="itemscope" itemtype="http://schema.org/ContactPage"&gt;
&lt;?php } <span class="pre-val">elseif</span> ( is_page('faq') ) { ?&gt;
	&lt;html &lt;?php language_attributes(); ?&gt; itemscope="itemscope" itemtype="http://schema.org/QAPage"&gt;
&lt;?php } <span class="pre-val">elseif</span> ( is_page('about-us') <span class="pre-val">||</span> is_page('privacy-policy') <span class="pre-val">||</span> is_page('terms-of-service')) {?&gt;
	&lt;html &lt;?php language_attributes(); ?&gt; itemscope="itemscope" itemtype="http://schema.org/AboutPage"&gt;
&lt;?php } <span class="pre-val">elseif</span> ( is_page('our-company') <span class="pre-val">||</span> is_page('our-team') <span class="pre-val">||</span> is_page('profile') ) { ?&gt;
	&lt;html &lt;?php language_attributes(); ?&gt; itemscope="itemscope" itemtype="http://schema.org/ProfilePage"&gt;
&lt;?php } <span class="pre-val">else</span> { ?&gt;
	&lt;html &lt;?php language_attributes(); ?&gt; itemscope="itemscope" itemtype="http://schema.org/WebPage"&gt;
&lt;?php } ?&gt;
</pre>
<p class="note">You should check the slugs on your site when adding this script, to be sure they match the ones added in this code.</p>
OK now, this works just fine, but looks like a little too much code, so let's clean it up a little. We'll create a function to configure the WebPage type and add it instead all this code, so instead of that thing above, it will now look like this:
<pre>&lt;?php 
<span class="pre-tag">function</span> <span class="pre-attr">page_type</span>() {
	<span class="pre-val">if</span> (is_front_page() <span class="pre-val">||</span> is_home()){<span class="pre-val">if</span>(<span class="pre-val">!</span>is_single()){$type <span class="pre-val">=</span> <span class="pre-type">"Blog"</span>;} <span class="pre-val">else</span> {$type <span class="pre-val">=</span> <span class="pre-type">"WebPage"</span>;}} 
	<span class="pre-val">elseif</span> (<span class="pre-val">!</span>is_single() <span class="pre-val">&amp;&amp;</span> <span class="pre-val">!</span>is_page() <span class="pre-val">&amp;&amp;</span> <span class="pre-val">!</span>is_search()) {$type <span class="pre-val">=</span> <span class="pre-type">"Blog"</span>;} 
	<span class="pre-val">elseif</span> (is_single() <span class="pre-val">&amp;&amp;</span> <span class="pre-val">!</span>is_search() <span class="pre-val">&amp;&amp;</span> <span class="pre-val">!</span>is_page_template('archive.php')) {$type <span class="pre-val">=</span> <span class="pre-type">"Blogposting"</span>;} 
	<span class="pre-val">elseif</span> (is_search() <span class="pre-val">||</span> is_page_template('archive.php')) {$type <span class="pre-val">=</span> <span class="pre-type">"SearchResultsPage"</span>;} 
	<span class="pre-val">elseif</span> (is_page('contact-us')) {$type <span class="pre-val">=</span> <span class="pre-type">"ContactPage"</span>;} 
	<span class="pre-val">elseif</span> (is_page('faq')) {$type <span class="pre-val">=</span> <span class="pre-type">"QAPage"</span>;} 
	<span class="pre-val">elseif</span> (is_page('about-us') <span class="pre-val">||</span> is_page('privacy-policy') <span class="pre-val">||</span> is_page('terms-of-service')) {$type <span class="pre-val">=</span> <span class="pre-type">"AboutPage"</span>;} 
	<span class="pre-val">elseif</span> (is_page('our-company') <span class="pre-val">||</span> is_page('our-team') <span class="pre-val">||</span> is_page('profile') ) {$type <span class="pre-val">=</span> <span class="pre-type">"ProfilePage"</span>;} 
	<span class="pre-val">else</span> {$type <span class="pre-val">=</span> <span class="pre-type">"WebPage"</span>;} 
	echo $type;
?&gt;
	&lt;html &lt;?php language_attributes(); ?&gt; itemscope="itemscope" itemtype="http://schema.org/&lt;?php page_type(); ?&gt;"&gt;
</pre>
It does look a lot better! Right?
If you know some php/wordpress, you can add this function to your theme's <em>function.php</em> file, and have this template a lot cleaner, because in your <em>header.php</em> file, you'll only have to call the function, so instead all that code, you'll only have this:
<pre>	&lt;html &lt;?php <span class="pre-val">language_attributes()</span>; ?&gt; itemscope="itemscope" itemtype="http://schema.org/&lt;?php <span class="pre-val">page_type()</span>; ?&gt;"&gt;
</pre>
</section><section>
<h4>SiteNavigationElement, WPHeader, WPFooter, and WPSideBar</h4>
These four schema.org types show the Search Engines where these webpage elements are situated, there's no real need to add a more complex markup on them, because the microdata parsers (the robots reading the structured data content on your website) know exactly what kind of content they find there.

While you still are in <em>header.php</em>, you should find the line <em>&lt;header id="home" class="header"&gt;</em>, and add the following attributes: <em>itemscope="itemscope" itemtype="http://schema.org/WPHeader"</em>.
The line you edited should now look like this:
<pre>&lt;header id="home" class="header" itemscope="itemscope" itemtype="http://schema.org/WPHeader"&gt;
</pre>
Now you go to your theme's file <em>footer.php</em> and find the next line <em>&lt;footer id="footer"&gt;</em> and change it tool look like this:
<pre>&lt;footer id="footer" itemscope="itemscope" itemtype="http://schema.org/WPFooter"&gt;
</pre>
The next thing you should find is the template used for mobile navigation in your theme; in my theme, the file is <em>template-tags.php</em>, but if your theme doesn't have a custom header, your mobile navigation should be in <em>header.php</em>. So, we find the HTML code defining the mobile navigation, and start adding our attributes.
<pre>&lt;nav class="navbar-collapse bs-navbar-collapse collapse" id="site-navigation"&gt;
</pre>
After adding the required attributes, the code will look like this:
<pre>&lt;nav class="navbar-collapse bs-navbar-collapse collapse" id="site-navigation" itemscope="itemscope" itemtype="http://schema.org/SiteNavigationElement"&gt;
</pre>
All that's left now is WPSideBar. We're going to look for the file called <em>sidebar.php</em>. When we found it, we'll search for the next line:
<pre>&lt;div id="secondary" class="widget-area" role="complementary"&gt;
</pre>
When we found it we'll add our attributes, and change it to look like this:
<pre>&lt;div id="secondary" class="widget-area" role="complementary" itemscope="itemscope" itemtype="http://schema.org/WPSideBar"&gt;
</pre>
And that's it for the complementary areas on your webpages.

</section><section>
<h4>Defining the schema.org microdata for content</h4>
Well, now that we added all complementary markup, and we defined the WebPage type for each of your pages, we must add some more microdata on the content, to comply to Google's requirements.
<p class="note">Schema.org and Google are 2 different organizations, Google's requirements are not necessarily schema's requirements, as this is just a simple RDF ontology, and the only thing required for a class to be valid is to have a name, or an ID.</p>
So, for a WebPage, in order to comply to Google requirements, we have to add some mandatory properties:
<ul>
 	<li>name</li>
 	<li>url</li>
 	<li>headline</li>
 	<li>mainEntityOfPage</li>
 	<li>datePublished</li>
 	<li>dateModified</li>
 	<li>image:ImageObject</li>
 	<li>author:Person » name, url</li>
 	<li>publisher:Organization » name, url, logo:ImageObject (image, url, width, height)</li>
</ul>
OK now, this seems a bit too much, and how are we going to find these elements in the templates?; because we don't want to touch the content, as all code added in the content will be lost every time you switch from Text mode to Visual mode, and back.

For start, we're going to find the templates used for each page/post. If you don't know which templates were used, you can use a very good plugin, called <a href="https://wordpress.org/plugins/what-the-file/" target="_blank" rel="nofollow noopener">What the File</a>, which will show you whatever template, and template parts were used for a page/post.

Anyway, on a simple wordpress theme, the template used for pages is <em>page.php</em> + <em>content-page.php</em>, and for posts, <em>single.php</em> + <em>content-single.php</em>.

First thing, we go to content-page.php, and find <em>&lt;span class="date published"&gt;</em>, or something similar, which is the part where the published date is shown on the page.
Here we add the next line: <em>itemprop="datePublished"</em>, so the code will look like this:
<pre>&lt;span class="date published" itemprop="datePublished"&gt;
</pre>
If we go to <em>content-single.php</em>, we also have a line for the title; so there we have to find the next line:
<pre>&lt;h1 class="entry-title"&gt;&lt;a href="&lt;?php the_permalink(); ?&gt;" rel="bookmark"&gt;&lt;?php the_title(); ?&gt;&lt;/a&gt;&lt;/h1&gt;
</pre>
... and we'll change it to:
<pre>&lt;h1 class="entry-title" itemprop="headline"&gt;&lt;a href="&lt;?php the_permalink(); ?&gt;" rel="bookmark" itemprop="url"&gt;&lt;?php the_title(); ?&gt;&lt;/a&gt;&lt;/h1&gt;
</pre>
Well now, it seems we have a problem: we have no headline, and url on content-page.php, and no date on the other template. We also have no name, no mainEntityOfPage, no author, and no publisher.
<p class="note">As themes are very different from one another, I suggest only doing the above steps if your theme keeps a standard wordpress format, or you would rather not do that, and add all info separately, like presented in the next section.</p>
The best way I figured for this issue is creating a hidden section with all info missing from pages; therefore, we will create this section, to add the missing info, and put it in our templates, as it follows:
<pre>&lt;section style="display:none"&gt;
&lt;meta itemprop="name" content="&lt;?php echo wp_title() ?&gt;"&gt;
&lt;meta itemprop="description" content="&lt;?php echo (htmlentities(strip_tags(the_excerpt())); ?&gt;"&gt;
&lt;meta itemprop="datePublished" content="&lt;?php echo get_the_date('YYYY-MM-DD'); ?&gt;"&gt;
&lt;meta itemprop="dateModified" content="&lt;?php echo get_the_modified_date('YYYY-MM-DD'); ?&gt;"&gt;
&lt;meta itemprop="headline" content="&lt;?php echo the_title(); ?&gt;"&gt;
&lt;meta itemprop="mainEntityOfPage" content="&lt;?php echo get_the_permalink(); ?&gt;post-&lt;?php the_ID(); ?&gt;"&gt;
&lt;p itemprop="author" itemscope="itemscope" itemtype="http://schema.org/Person"&gt;
	&lt;meta itemprop="name" content="&lt;?php echo get_the_author_meta('display_name', $auth_id); ?&gt;" /&gt;
	&lt;link itemprop="url" href="&lt;?php echo get_the_author_url();?&gt;" /&gt;
&lt;/p&gt;
&lt;div itemprop="publisher" itemscope="itemscope" itemtype="http://schema.org/Organization"&gt;
	&lt;span itemprop="name"&gt;kazenokodomo&lt;/span&gt;
	&lt;link itemprop="url" href="http://purls.site/" /&gt;
	&lt;figure itemprop="logo" itemscope="itemscope" itemtype="http://schema.org/ImageObject"&gt;
		&lt;a href="http://purls.site" itemprop="url"&gt;&lt;img itemprop="image" src="http://purls.site/wp-content/uploads/2017/03/knk-logo.png" /&gt;
		&lt;meta itemprop="width" content="35" /&gt;&lt;meta itemprop="height" content="35" /&gt;&lt;/a&gt;
	&lt;/figure&gt;
&lt;/div&gt;
&lt;?php 
	global $post;
	$image_data = wp_get_attachment_image_src( get_post_thumbnail_id( $post-&gt;ID ), "wp_post_image" );
	$image_source = $image_data[0];
	$image_width = $image_data[1];
	$image_height = $image_data[2];
?&gt;
&lt;div itemprop="image" itemscope itemtype="http://schema.org/ImageObject"&gt;
    &lt;a itemprop="url" href="&lt;?php the_permalink(); ?&gt;" title="&lt;?php the_title_attribute(); ?&gt;" &gt;
	&lt;img itemprop="image" src="&lt;?php echo $image_source; ?&gt;" /&gt;
	&lt;meta itemprop="width" content="&lt;?php echo $image_width; ?&gt;" /&gt;
	&lt;meta itemprop="height" content="&lt;?php echo $image_height; ?&gt;" /&gt;
    &lt;/a&gt;
&lt;/div&gt;
&lt;/section&gt;
</pre>
<p class="note">You should change the Organization info with whatever organization supports you (I added mine).</p>
To explain a little the code above:
<dl>
 	<dt>name</dt>
 	<dd>I used the wp_title() function which displays the page's title as in the &lt;head&gt; section of the page</dd>
 	<dt>description</dt>
 	<dd>I used the the_excerpt() function, from which I removed all html tags, and changed all symbols to ascii code</dd>
 	<dt>datePublished</dt>
 	<dd>I used the get_the_date() function which displays the date when the article/page was created</dd>
 	<dt>dateModified</dt>
 	<dd>I used the get_the_modified_date() function which displays the date when the page/article was last modified</dd>
 	<dt>headline</dt>
 	<dd>I used the title of the article/page</dd>
 	<dt>mainEntityOfPage</dt>
 	<dd>I used the ID of the content section of the page/article</dd>
 	<dt>author</dt>
 	<dd>I used the functions that display the post author info</dd>
 	<dt>publisher</dt>
 	<dd>I used static info that will be repeated on all pages (change it to your organization's info)</dd>
 	<dt>image</dt>
 	<dd>I created a small function to get the attributes of the featured image (if you don't have a featured image, you should add one, or expand the function using DOM Api or RegExp to find the images in the content)</dd>
</dl>
</section><section>
<h4>The Loop</h4>
For creating the structured data on the loop, we have to edit <em>index.php</em>, and <em>content.php</em>, which loads all the blog posts on this page.
So, the only file we need to edit for the loop is <em>content.php</em>. In this file we will actually configure the Blog structured data markup. When we have articles (or any article sub-type) Google is very strict with the mandatory properties. We will configure the loop, in order to automatically add correct, and complete structured data for all elements in the loop.
First we must declare the main container as a child of the Blog, so we have to configure it on the first line of the template:
<pre>&lt;article id="post-&lt;?php the_ID(); ?&gt;" &lt;?php post_class(); ?&gt; itemprop="blogPost" itemscope itemtype="http://schema.org/BlogPosting"&gt;
</pre>
Considering that an article should have: <a href="http://schema.org/name" target="_blank" rel="nofollow noopener">name</a>, <a href="http://schema.org/url" target="_blank" rel="nofollow noopener">url</a>, <a href="http://schema.org/headline" target="_blank" rel="nofollow noopener">headline</a>, <a href="http://schema.org/mainEntityOfPage" target="_blank" rel="nofollow noopener">mainEntityOfPage</a>, <a href="http://schema.org/ImageObject" target="_blank" rel="nofollow noopener">image::ImageObject</a>, <a href="http://schema.org/Person" target="_blank" rel="nofollow noopener">author::Person</a>, <a href="http://schema.org/ImageObject" target="_blank" rel="nofollow noopener">publisher::Organization</a>, <a href="http://schema.org/datePublished" target="_blank" rel="nofollow noopener">datePublished</a>, and <a href="http://schema.org/dateModified" target="_blank" rel="nofollow noopener">dateModified</a>, we have to add some extra lines to the template.

<em>The name and the headline properties</em> will be added to the entry-title from within the loop, like this:
<pre>&lt;h1 <span class="pre-attr">itemprop="name headline"</span> class="entry-title"&gt;&lt;a href="&lt;?php the_permalink(); ?&gt;" rel="bookmark"&gt;&lt;?php the_title(); ?&gt;&lt;/a&gt;&lt;/h1&gt;
</pre>
<p class="note">We'll use the same code for both name and headline, because we can't find a headline in the displayed excerpt, but it is a mandatory property.</p>
<em>The url property</em> will be added on the same line as the name, on the permalink, as it has to describe the direct link to the page. After adding it, the line will look like this:
<pre>&lt;h1 <span class="pre-attr">itemprop="name headline"</span> class="entry-title"&gt;&lt;a <span class="pre-attr">itemprop="url"</span> href="&lt;?php the_permalink(); ?&gt;" rel="bookmark"&gt;&lt;?php the_title(); ?&gt;&lt;/a&gt;&lt;/h1&gt;
</pre>
<em>The mainEntityOfPage property</em> will be added lower in the template, where the div with the entry-content class is, so we'll change it to:
<pre>&lt;div class="entry-content" <span class="pre-attr">itemprop="mainEntityOfPage"</span>&gt;
</pre>
<em>The image property</em> is mandatory for all articles, therefore we'll make use of the post featured image. In order to validate the article image, we must give it an itemtype, and declare it as an <em>ImageObject</em>, which must have the following properties: <em>image</em>, <em>url</em>, <em>width</em>, and <em>height</em>. We will make use of the already existent script, and add some extra lines of code, to pick the info we need. This is the part where we will configure the <em>ImageObject</em>.

First, we will call a wordpress specific function to fetch the attached image's attributes, so we can get its width, and height; we also have to get the post thumbnail url, because we can't use the $post_thumbnail_url function existent on the page. After all this is done, our code should look like this:
<pre>    &lt;?php 
    $image_data = wp_get_attachment_image_src( get_post_thumbnail_id( $post-&gt;ID ), "wp_post_image" ); 
    $image_width = $image_data[1];
    $image_height = $image_data[2]; ?&gt;
        &lt;div itemprop="image" itemscope itemtype="http://schema.org/ImageObject"&gt;
            &lt;a itemprop="url" href="&lt;?php the_permalink(); ?&gt;" title="&lt;?php the_title_attribute(); ?&gt;" &gt;
			&lt;img itemprop="image" src="&lt;?php echo get_the_post_thumbnail_url(); ?&gt;"&gt;
			&lt;meta itemprop="width" content="&lt;?php echo $image_width; ?&gt;"&gt;
			&lt;meta itemprop="height" content="&lt;?php echo $image_height; ?&gt;"&gt;
            &lt;/a&gt;
        &lt;/div&gt;
</pre>
<em>The author property</em> can be added in a section set to <em>display:none</em>, together with the <em>publisher</em>, <em>datePublished</em>, and <em>dateModified</em> properties.

Therefore, we create a section for all these properties; we also need a description for the article, and for this we'll declare the article excerpt as the description, so we get the excerpt from wordpress and create a new entity:
<pre>&lt;div itemprop="description"&gt;&lt;?php echo excerpt() ?&gt;&lt;/div&gt;
</pre>
After all this is done, our entity will look like this:
<pre>&lt;section class="meta-information" style="display:none;"&gt;
&lt;div itemprop="description"&gt;&lt;?php echo the_excerpt(); ?&gt;&lt;/div&gt;
&lt;p itemprop="author" itemscope itemtype="http://schema.org/Person"&gt;
	&lt;span itemprop="name"&gt;&lt;?php echo get_author_name(); ?&gt;&lt;/span&gt;
&lt;/p&gt;
&lt;div itemprop="publisher" itemscope itemtype="http://schema.org/Organization"&gt;
	&lt;meta itemprop="name" content="kazenokodomo" /&gt;
	&lt;link itemprop="url" href="http://purls.site" /&gt;
	&lt;figure itemprop="logo" itemscope itemtype="http://schema.org/ImageObject"&gt;
		&lt;a href="http://purls.site" itemprop="url"&gt;
			&lt;img src="http://purls.site/wp-content/uploads/2017/03/logo.png" itemprop="image"&gt;
		&lt;/a&gt;
	&lt;/figure&gt;
&lt;/div&gt;
&lt;meta itemprop="datePublished" content="&lt;?php echo get_the_date(); ?&gt;" /&gt;
&lt;meta itemprop="dateModified" content="&lt;?php echo get_the_modified_date(); ?&gt;" /&gt;
    &lt;?php $image_data = wp_get_attachment_image_src( get_post_thumbnail_id( $post-&gt;ID ), "wp_post_image" );
    $image_width = $image_data[1];
    $image_height = $image_data[2]; ?&gt;
        &lt;div itemprop="image" itemscope itemtype="http://schema.org/ImageObject"&gt;
            &lt;a itemprop="url" href="&lt;?php the_permalink(); ?&gt;" title="&lt;?php the_title_attribute(); ?&gt;" &gt;
			&lt;img itemprop="image" src="&lt;?php echo get_the_post_thumbnail_url(); ?&gt;"&gt;
			&lt;meta itemprop="width" content="&lt;?php echo $image_width; ?&gt;"&gt;&lt;meta itemprop="height" content="&lt;?php echo $image_height; ?&gt;"&gt;
            &lt;/a&gt;
        &lt;/div&gt;
&lt;/section&gt;
</pre>
<p class="note">We have to set this info inside the loop, because the function <em>while have_posts : the_post()</em> resets after each post loaded.</p>

</section><section>
<h4>Fixing the Structured Data for Tag, Category, and Search Results Pages</h4>

<hr />

Ok, now, as we fixed the markup for BlogPosting, and Blog, we still have Tag, Category, and Search Results Pages.

For the <em>Search Results Pages</em>, we need to open the <em>search.php</em> file, and add some attributes, as it follows:
<ol>
 	<li>&lt;div id="content" class="site-content"&gt; becomes
&lt;div id="content" class="site-content" itemscope itemtype="http://schema.org/Blog"&gt;</li>
 	<li>&lt;h1 class="page-title"&gt; becomes &lt;h1 itemprop="name" class="page-title"&gt;</li>
</ol>
For the <em>Tag &amp; Catyegory Pages</em>, we need to open the <em>archive.php</em> file, and add some attributes, as it follows:
<ol>
 	<li>&lt;div id="content" class="site-content"&gt; becomes
&lt;div id="content" class="site-content" itemscope itemtype="http://schema.org/Blog"&gt;</li>
 	<li>For the name, we will add a new line just after declaring the <em>Blog</em> type:
&lt;meta itemprop="name" content="&lt;?php echo wp_title(); ?&gt;" /&gt;</li>
</ol>
&nbsp;
<blockquote>If you made all these alterations to the templates, your blog should now have a somehow complete, but 100% correct schema.org structured data implementation.

If you want to complete it even more, you can add properties as attributes on links, images, videos, actions or other important elements in your page content, by using the Text Mode when editing your Wordpress posts.
<p class="note">Note: All the attributes added in the Edit mode will be lost whenever you switch to Visual mode, and back.</p>
</blockquote>
</section>