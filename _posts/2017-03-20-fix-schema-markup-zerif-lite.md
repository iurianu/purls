---
ID: 1
post_title: >
  Fix Schema.org Markup on Zerif Lite
  Theme
author: iurianu
post_excerpt: ""
layout: post
permalink: >
  http://purls.site/fix-schema-markup-zerif-lite/
published: true
post_date: 2017-03-20 14:42:22
---
I found that writing this article is a necessity, because most of the schema.org structured data coming with the WordPress themes is very incomplete, and with lots of errors, or it's completely missing. I will focus on the Blog Template (index.php), with its content template (content.php), and the post template (single.php), including the content template (content-single.php).

I am working on the <a href="https://themeisle.com/themes/zerif-lite/" target="_blank" rel="nofollow noopener">Zerif Lite Theme</a> (Version 1.8.5.16), which comes with some schema.org structured data implemented, which we must fix:
<h4>1. File: index.php</h4>
This file is used to loop through all your blog postings, and in this particular theme, the index file is replaced by a custom template (front-page.php), as the Blog is used as a static front page.
Here we should have the next line
<pre>&lt;main id="main" class="site-main" itemscope itemtype="http://schema.org/Blog"&gt;
</pre>
In any case, you should add the same line on the Posts Page Template (home.php)
<h4>2. File: content.php</h4>
In this file we will actually configure the Blog structured data markup. When we have articles (or any article sub-type) schema.org is very strict with the mandatory properties. We will configure the loop, in order to automatically add correct, and complete structured data for all elements in the loop.
First of everything, we must declare the main container as a child of the Blog, so we have to configure it on the first line of the template:
<pre>&lt;article id="post-&lt;?php the_ID(); ?&gt;" &lt;?php post_class(); ?&gt; itemprop="blogPost" itemscope itemtype="http://schema.org/BlogPosting"&gt;
</pre>
Considering that an article should have: name, url, headline, mainEntityOfPage, image::ImageObject, author::Person, publisher::Organization, datePublished, and dateModified, we have to add some extra lines to the template.

2.1. <em>The name property</em> will be added to the entry-title from within the loop, like this:
<pre>&lt;h1 itemprop="name" class="entry-title"&gt;&lt;a href="&lt;?php the_permalink(); ?&gt;" rel="bookmark"&gt;&lt;?php the_title(); ?&gt;&lt;/a&gt;&lt;/h1&gt;
</pre>
2.2. <em>The url property</em> will be added on the same line as the name, on the permalink, as it has to describe the direct link to the page. After adding it, the line will look like this:
<pre>&lt;h1 itemprop="name" class="entry-title"&gt;&lt;a itemprop="url" href="&lt;?php the_permalink(); ?&gt;" rel="bookmark"&gt;&lt;?php the_title(); ?&gt;&lt;/a&gt;&lt;/h1&gt;
</pre>
2.3. <em>The headline property</em> will be added on the same line as the name, and the url, because it's hard to find all the headlines in the article, so we'll do this trick to validate the code, without having to write nonsense. After adding it, the line will look like this:
<pre>&lt;h1 itemprop="name headline" class="entry-title"&gt;&lt;a itemprop="url" href="&lt;?php the_permalink(); ?&gt;" rel="bookmark"&gt;&lt;?php the_title(); ?&gt;&lt;/a&gt;&lt;/h1&gt;
</pre>
2.4. <em>The mainEntityOfPage property</em> will be added lower in the template, where the div with the entry-content class is, so we'll change it to:
<pre>&lt;div class="entry-content" itemprop="mainEntityOfPage"&gt;
</pre>
2.5. <em>The image property</em> is mandatory for all articles, therefore we'll make use of the post featured image. In order to validate the article image, we must give it an itemtype, and declare it as an <em>ImageObject</em>, which must have the following properties: <em>image</em>, <em>url</em>, <em>width</em>, and <em>height</em>. We will make use of the already existent script, and add some extra lines of code, to pick the info we need. This is the part where we will configure the <em>ImageObject</em>.

First, we will call a wordpress specific function to fetch the attached image's attributes, so we can get its width, and height; we also have to get the post thumbnail url, because we can't use the $post_thumbnail_url function existent on the page. After all this is done, our code should look like this:
<pre>    &lt;?php $image_data = wp_get_attachment_image_src( get_post_thumbnail_id( $post-&gt;ID ), "wp_post_image" ); ?&gt;
    &lt;?php $image_width = $image_data[1]; ?&gt;
    &lt;?php $image_height = $image_data[2]; ?&gt;
        &lt;div itemprop="image" itemscope itemtype="http://schema.org/ImageObject"&gt;
            &lt;a itemprop="url" href="&lt;?php the_permalink(); ?&gt;" title="&lt;?php the_title_attribute(); ?&gt;" &gt;
			&lt;img itemprop="image" src="&lt;?php echo get_the_post_thumbnail_url(); ?&gt;"&gt;
			&lt;meta itemprop="width" content="&lt;?php echo $image_width; ?&gt;"&gt;&lt;meta itemprop="height" content="&lt;?php echo $image_height; ?&gt;"&gt;
            &lt;/a&gt;
        &lt;/div&gt;
</pre>
2.6. <em>The author property</em> can be added in a section set to not be displayed, together with the <em>publisher</em>, <em>datePublished</em>, and <em>dateModified</em> properties.

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
    &lt;?php $image_data = wp_get_attachment_image_src( get_post_thumbnail_id( $post-&gt;ID ), "wp_post_image" ); ?&gt;
    &lt;?php $image_width = $image_data[1]; ?&gt;
    &lt;?php $image_height = $image_data[2]; ?&gt;
        &lt;div itemprop="image" itemscope itemtype="http://schema.org/ImageObject"&gt;
            &lt;a itemprop="url" href="&lt;?php the_permalink(); ?&gt;" title="&lt;?php the_title_attribute(); ?&gt;" &gt;
			&lt;img itemprop="image" src="&lt;?php echo get_the_post_thumbnail_url(); ?&gt;"&gt;
			&lt;meta itemprop="width" content="&lt;?php echo $image_width; ?&gt;"&gt;&lt;meta itemprop="height" content="&lt;?php echo $image_height; ?&gt;"&gt;
            &lt;/a&gt;
        &lt;/div&gt;
&lt;/section&gt;
</pre>
<h4>3. File: single.php</h4>
This template starts with:
<pre>&lt;div id="content" class="site-content" itemtype="http://schema.org/BlogPost" itemtype="http://schema.org/BlogPost"&gt;
</pre>
which means nothing for either the structured data validators or for the search engines, as all types should be declared together with an itemscope, and BlogPost is not a valid schema.org type.

Now, in order to fix this, we'll delete one of the 2 types, fix the other one, and add the itemscope to the code; after that, it should look like this:
<pre>&lt;div id="content" class="site-content" itemscope itemtype="http://schema.org/BlogPosting"&gt;
</pre>
or like this:
<pre>&lt;div id="content" class="site-content" itemscope itemtype="http://schema.org/Article"&gt;
</pre>
<p class="note">Note: When declaring the type for your blog posts you can chose whatever sub-type of Article provided within the schema.org vocabulary.</p>

<figure><figcaption>This is how Google's Structured Data Testing Tool reads your Blog Post now:</figcaption>
<a href="http://purls.site/wp-content/uploads/2017/03/blogpost-errors.png"><img src="http://purls.site/wp-content/uploads/2017/03/blogpost-errors.png" alt="BlogPost Errors" width="913" height="571" class="alignnone size-full wp-image-59" /></a>
</figure>
Lower in this file, we see the next line:
<pre>&lt;main id="main" class="site-main" itemprop="mainContentOfPage"  itemscope itemtype="http://schema.org/WebPageElement"&gt;
</pre>
This declares the article content as a <em>WebPageElement</em>, where all the text, images, videos etc. will be ignored, and the real content will be tagged as <em>name</em>, with a property not supported by the <em>BlogPosting</em> type.

To fix this we will change the property to <em>mainEntityOfPage</em>, and get rid of the itemscope and itemtype.

,The line of code should now look like this:
<pre>&lt;main id="main" class="site-main" itemprop="mainEntityOfPage"&gt;
</pre>
<h4>4. File: content-single.php</h4>
In this file we will add all structured data for a single article (blog posting).

First, we need to add the name, and the headline properties on the first line in the header:
<pre>&lt;h1 itemprop="name headline" class="entry-title"&gt;&lt;?php the_title(); ?&gt;&lt;/h1&gt;
</pre>
Second, we will add all meta data in a hidden section, which should look like this:
<pre>&lt;section class="meta-information" style="display:none;"&gt;
&lt;div itemprop="description"&gt;&lt;?php echo the_excerpt(); ?&gt;&lt;/div&gt;
&lt;p itemprop="author" itemscope itemtype="http://schema.org/Person"&gt;
	&lt;span itemprop="name"&gt;&lt;?php echo get_author_name(); ?&gt;&lt;/span&gt;&lt;/p&gt;
&lt;div itemprop="publisher" itemscope itemtype="http://schema.org/Organization"&gt;
	&lt;meta itemprop="name" content="kazenokodomo" /&gt;	&lt;link itemprop="url" href="http://purls.site" /&gt;
	&lt;figure itemprop="logo" itemscope itemtype="http://schema.org/ImageObject"&gt;&lt;a href="http://purls.site" itemprop="url"&gt;
	&lt;image src="http://purls.site/wp-content/uploads/2017/03/logo.png" itemprop="image"&gt;&lt;/a&gt;&lt;/figure&gt;&lt;/div&gt;
&lt;meta itemprop="datePublished" content="&lt;?php echo get_the_date(); ?&gt;" /&gt;
&lt;meta itemprop="dateModified" content="&lt;?php echo get_the_modified_date(); ?&gt;" /&gt;
&lt;figure itemprop="image" itemscope itemtype="http://schema.org/ImageObject"&gt;
 	&lt;?php $image_data = wp_get_attachment_image_src( get_post_thumbnail_id( $post-&gt;ID ), "wp_post_image" ); ?&gt;
	 &lt;?php $image_width = $image_data[1]; ?&gt;
 	&lt;?php $image_height = $image_data[2]; ?&gt; 
	 &lt;a itemprop="url" href="&lt;?php the_permalink(); ?&gt;"&gt;
	&lt;img itemprop="image" src="&lt;?php echo get_the_post_thumbnail_url(); ?&gt;"&gt;
	&lt;meta itemprop="width" content="&lt;?php echo $image_width; ?&gt;"&gt;
	&lt;meta itemprop="height" content="&lt;?php echo $image_height; ?&gt;"&gt;&lt;/a&gt;&lt;/figure&gt;
&lt;/section&gt;
</pre>
&nbsp;

<hr />

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