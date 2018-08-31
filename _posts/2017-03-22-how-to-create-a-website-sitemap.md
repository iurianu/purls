---
ID: 389
post_title: How to Create a Website Sitemap
author: iurianu
post_excerpt: ""
layout: post
permalink: >
  https://purls.site/structured-data/xml-rdf/how-to-create-a-website-sitemap/
published: true
post_date: 2017-03-22 12:34:08
---
The best ways to let the Crawlers know which pages on your Website should be crawled, and which shouldn't, are editing your robots.txt file, or creating a sitemap.

<figure><a href="http://purls.site/wp-content/uploads/2017/03/sitemap-image-1.jpg"><img src="http://purls.site/wp-content/uploads/2017/03/sitemap-image-1.jpg" alt="Sitemap Image" width="495" height="191" class="alignnone size-full wp-image-391" /></a></figure>

Here I will explain how to create a simple XML sitemap for your site.
<blockquote>
<p class="note">Google recommends limiting the sitemaps to 50,000 entries; if you have very much information on your website, or if maybe you want to structure your sitemap in a particular way, you can create more sitemaps (i.e. per category, tag, image-sitemap, video-sitemap etc.), and gather them all in a sitemap-index.</p>
</blockquote>
&nbsp;

First, you must create a txt file and call it sitemap.xml, and edit it with any available text editor (I recommend Brackets, Sublime Text, or Notepad++).

When you start editing the xml file, you must declare the version and encoding for it, so the crawlers know how to read the file:
<span style="color: green; text-align: center;">&lt;?xml version="1.0" encoding="UTF-8"?&gt;</span>;

After declaring the XML version, you start writing your sitemap by opening an url set, and declaring the namespace for sitemaps:
<span style="color: green; text-align: center;">&lt;urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9"&gt;</span>.

When the url set is opened, you start adding your url's to the sitemap:
<ul>
 	<li><span style="color: green;">&lt;url&gt;</span> - to declare the block containing an url's properties;</li>
 	<li><span style="color: green;">&lt;loc&gt;</span> - the link for the url's location;</li>
 	<li><span style="color: green;">&lt;lastmod&gt;</span> - the date the page was last modified;</li>
 	<li><span style="color: green;">&lt;changefreq&gt;</span> - the change frequency for the page (can take values as daily, weekly, monthly, yearly, always, or never);</li>
 	<li><span style="color: green;">&lt;priority&gt;</span> - the priority among other pages on the website (can take values between 0 and 1).</li>
</ul>
<p class="note">Note: Only <em>&lt;url&gt;</em> and <em>&lt;loc&gt;</em> are mandatory fields.</p>
You can add as many url's as needed, by opening and closing the <span style="color: green;">&lt;url&gt;</span> tag.

After finishing, your sitemap's code should look like this:
<pre><code>
&lt;?xml <span class="tag">version</span>="<span class="tag-attr">1.0</span>" <span class="tag">encoding</span>="<span class="tag-attr">UTF-8</span>"?&gt;
&lt;urlset <span class="tag">xmlns</span>="<span class="tag-attr">http://www.sitemaps.org/schemas/sitemap/0.9</span>"&gt;
   &lt;url&gt;
      &lt;loc&gt;<span class="tag-attr">http://www.example.com/</span>&lt;/loc&gt;
      &lt;lastmod&gt;<span class="tag-attr">2016-05-01</span>&lt;/lastmod&gt;
      &lt;changefreq&gt;<span class="tag-attr">monthly</span>&lt;/changefreq&gt;
      &lt;priority&gt;<span class="tag-attr">0.8</span>&lt;/priority&gt;
   &lt;/url&gt;
   .
   .
   .
   &lt;url&gt;
      &lt;loc&gt;<span class="tag-attr">http://www.example.com/about/</span>&lt;/loc&gt;
      &lt;lastmod&gt;<span class="tag-attr">2016-05-03</span>&lt;/lastmod&gt;
      &lt;changefreq&gt;<span class="tag-attr">never</span>&lt;/changefreq&gt;
      &lt;priority&gt;<span class="tag-attr">0.9</span>&lt;/priority&gt;
   &lt;/url&gt;
&lt;/urlset&gt; 
</code></pre>
<h4>Adding Images to Sitemap</h4>
If you want to add images to your sitemap, you must add a new namespace, for images:
<span style="color: green; text-align: center;">xmlns:image="http://www.google.com/schemas/sitemap-image/1.1"</span>.

After adding the new namespace, you can start adding the images to the sitemap:
<ul>
 	<li><span style="color: green;">&lt;image:image&gt;</span> - to declare the block containing an image's properties;</li>
 	<li><span style="color: green;">&lt;image:loc&gt;</span> - the link for the image's location (could be an IRI);</li>
 	<li><span style="color: green;">&lt;image:title&gt;</span> - the title of the image;</li>
 	<li><span style="color: green;">&lt;image:caption&gt;</span> - the caption of the image;</li>
 	<li><span style="color: green;">&lt;image:geo_location&gt;</span> - the geographic location of the image;</li>
 	<li><span style="color: green;">&lt;image:license&gt;</span> - an URL to the license of the image.</li>
</ul>
<em>* Only <span style="color: green;">&lt;image:image&gt;</span> and <span style="color: green;">&lt;image:loc&gt;</span> are mandatory fields.</em>

After adding images, your sitemap must look like this:
<pre><code>
&lt;?xml <span class="tag">version</span>="<span class="tag-attr">1.0</span>" <span class="tag">encoding</span>="<span class="tag-attr">UTF-8</span>"?&gt;
&lt;urlset <span class="tag">xmlns</span>="<span class="tag-attr">http://www.sitemaps.org/schemas/sitemap/0.9</span> 
         <span class="tag">xmlns:image</span>="<span class="tag-attr">http://www.google.com/schemas/sitemap-image/1.1</span>"&gt;
   &lt;url&gt;
      &lt;loc&gt;<span class="tag-attr">http://www.example.com/</span>&lt;/loc&gt;
      &lt;lastmod&gt;<span class="tag-attr">2017-03-20</span>&lt;/lastmod&gt;
      &lt;changefreq&gt;<span class="tag-attr">monthly</span>&lt;/changefreq&gt;
      &lt;priority&gt;<span class="tag-attr">0.8</span>&lt;/priority&gt;
      &lt;image:image&gt;
        &lt;image:loc&gt;<span class="tag-attr">http://example.com/image.jpg</span>&lt;/image:loc&gt;
      &lt;/image:image&gt;
      &lt;image:image&gt;
        &lt;image:loc&gt;<span class="tag-attr">http://example.com/photo.jpg</span>&lt;/image:loc&gt;
        &lt;image:title&gt;<span class="tag-attr">The Palace of Culture from Iaşi, România</span>&lt;/image:title&gt;
        &lt;image:caption&gt;<span class="tag-attr">A photo of the Palace of Culture</span>&lt;/image:caption&gt;
        &lt;image:geo_location&gt;<span class="tag-attr">Iaşi, România</span>&lt;/image:geo_location&gt;
        &lt;image:license&gt;<span class="tag-attr">http://www.iurianu.info</span>&lt;/image:license&gt;
      &lt;/image:image&gt;
   &lt;/url&gt;
   .
   .
   .
   &lt;url&gt;
      &lt;loc&gt;<span class="tag-attr">http://www.example.com/about/</span>&lt;/loc&gt;
      &lt;lastmod&gt;<span class="tag-attr">2017-03-22</span>&lt;/lastmod&gt;
      &lt;changefreq&gt;<span class="tag-attr">never</span>&lt;/changefreq&gt;
      &lt;priority&gt;<span class="tag-attr">0.9</span>&lt;/priority&gt;
   &lt;/url&gt;
&lt;/urlset&gt; 
</code></pre>
<h4>Adding Videos to Sitemap</h4>
If you want to add videos to your sitemap, you must add yet another namespace, for videos:
<span style="color: green; text-align: center;">xmlns:video="http://www.google.com/schemas/sitemap-video/1.1"</span>.

When adding videos in your sitemap, there are 5 mandatory attributes:
<ul>
 	<li><span style="color: green;">&lt;video:video&gt;</span> - encloses all information about the video;</li>
 	<li><span style="color: green;">&lt;video:thumbnail_loc&gt;</span> - an URL pointing to the video thumbnail image file; images must be at least 160x90px and at most 1920x1080px.</li>
 	<li><span style="color: green;">&lt;video:title&gt;</span> - the title of the video;</li>
 	<li><span style="color: green;">&lt;video:description&gt;</span> - the description of the video;</li>
 	<li><span style="color: green;">&lt;video:content_loc&gt;</span> - an URL pointing to the actual video media file;</li>
 	<li><span style="color: green;">&lt;video:player_loc&gt;</span> - an URL pointing to a player for a specific video (the information in the src element of an <span style="color: green;">&lt;embed&gt;</span> tag).</li>
</ul>
For Youtube videos, you can use one of its default images, which are formatted like this:
<ul style="list-style-type: square;">
 	<li>https://img.youtube.com/vi/&lt;video-id&gt;/default.jpg</li>
 	<li>https://img.youtube.com/vi/&lt;video-id&gt;/0.jpg - full size imgae</li>
 	<li>https://img.youtube.com/vi/&lt;video-id&gt;/1.jpg - thumbnail</li>
 	<li>https://img.youtube.com/vi/&lt;video-id&gt;/2.jpg - thumbnail</li>
 	<li>https://img.youtube.com/vi/&lt;video-id&gt;/3.jpg - thumbnail</li>
 	<li>https://img.youtube.com/vi/&lt;video-id&gt;/hqdefault.jpg - high quality thumbnail</li>
 	<li>https://img.youtube.com/vi/&lt;video-id&gt;/mqdefault.jpg - medium quality thumbnail</li>
 	<li>https://img.youtube.com/vi/&lt;video-id&gt;/sddefault.jpg - standard definition version of thumbnail</li>
 	<li>https://img.youtube.com/vi/&lt;video-id&gt;/maxresdefault.jpg - max resolution thumbnail (some videos)</li>
</ul>
<blockquote>
<p class="note">It's enough to specify only one of <span style="color: green;">video:content_loc</span> and <span style="color: green;">video:player_loc</span>.</p>
</blockquote>
Other recommended, and optional attributes for video sitemaps are:
<ul>
 	<li>video:duration</li>
 	<li>video:expiration_date</li>
 	<li>video:rating</li>
 	<li>video:view_count</li>
 	<li>video:publication_date</li>
 	<li>video:family_friendly</li>
 	<li>video:tag</li>
 	<li>video:category</li>
 	<li>video:restriction</li>
 	<li>video:gallery_loc</li>
 	<li>video:price</li>
 	<li>video:requires_subscription</li>
 	<li>video:uploader</li>
 	<li>video:platform</li>
 	<li>video:live</li>
</ul>
After adding videos, your sitemap must look like this:
<pre><code>
&lt;?xml <span class="tag">version</span>="<span class="tag-attr">1.0</span>" <span class="tag">encoding</span>="<span class="tag-attr">UTF-8</span>"?&gt;
&lt;urlset <span class="tag">xmlns</span>="<span class="tag-attr">http://www.sitemaps.org/schemas/sitemap/0.9</span> 
         <span class="tag">xmlns:image</span>="<span class="tag-attr">http://www.google.com/schemas/sitemap-image/1.1</span>"
         <span class="tag">xmlns:video</span>="<span class="tag-attr">http://www.google.com/schemas/sitemap-video/1.1</span>"&gt;
   &lt;url&gt;
      &lt;loc&gt;<span class="tag-attr">http://www.example.com/</span>&lt;/loc&gt;
      &lt;lastmod&gt;<span class="tag-attr">2017-03-20</span>&lt;/lastmod&gt;
      &lt;changefreq&gt;<span class="tag-attr">monthly</span>&lt;/changefreq&gt;
      &lt;priority&gt;<span class="tag-attr">0.8</span>&lt;/priority&gt;
      &lt;image:image&gt;
        &lt;image:loc&gt;<span class="tag-attr">http://example.com/image.jpg</span>&lt;/image:loc&gt;
      &lt;/image:image&gt;
      &lt;image:image&gt;
        &lt;image:loc&gt;<span class="tag-attr">http://example.com/photo.jpg</span>&lt;/image:loc&gt;
        &lt;image:title&gt;<span class="tag-attr">The Palace of Culture from Iaşi, România</span>&lt;/image:title&gt;
        &lt;image:caption&gt;<span class="tag-attr">A photo of the Palace of Culture</span>&lt;/image:caption&gt;
        &lt;image:geo_location&gt;<span class="tag-attr">Iaşi, România</span>&lt;/image:geo_location&gt;
        &lt;image:license&gt;<span class="tag-attr">http://www.iurianu.info</span>&lt;/image:license&gt;
      &lt;/image:image&gt;
   &lt;/url&gt;
   .
   .
   .
   &lt;url&gt;
      &lt;loc&gt;<span class="tag-attr">http://www.example.com/about/</span>&lt;/loc&gt;
      &lt;lastmod&gt;<span class="tag-attr">2017-03-22</span>&lt;/lastmod&gt;
      &lt;changefreq&gt;<span class="tag-attr">never</span>&lt;/changefreq&gt;
      &lt;priority&gt;<span class="tag-attr">0.9</span>&lt;/priority&gt;
      &lt;video:video&gt;
         &lt;video:thumbnail_loc&gt;<span class="tag-attr">http://www.example.com/thumbs/123.jpg</span>&lt;/video:thumbnail_loc&gt; 
         &lt;video:title&gt;<span class="tag-attr">Walking in the Air</span>&lt;/video:title&gt;
         &lt;video:description&gt;
            <span class="tag-attr">The song 'Walking In The Air' from the animated short 'The Snowman' by Raymond Briggs. It was written by Howard Blake and in this recording sung by Peter Auty.</span>
         &lt;/video:description&gt;
         &lt;video:content_loc&gt;<span class="tag-attr">https://www.youtube.com/watch?v=ubeVUnGQOIk</span>&lt;/video:content_loc&gt;
         &lt;video:player_loc <span class="tag">allow_embed</span>="<span class="tag-attr">yes</span>" <span class="tag">autoplay</span>="<span class="tag-attr">ap=1</span>"&gt;<span class="tag-attr">https://www.youtube.com/embed/ubeVUnGQOIk</span>&lt;/video:player_loc&gt;
         &lt;video:duration&gt;<span class="tag-attr">225</span>&lt;/video:duration&gt;
         &lt;video:rating&gt;<span class="tag-attr">5.0</span>&lt;/video:rating&gt; 
         &lt;video:view_count&gt;<span class="tag-attr">8873470</span>&lt;/video:view_count&gt;    
         &lt;video:publication_date&gt;<span class="tag-attr">2008-12-17</span>&lt;/video:publication_date&gt;
         &lt;video:family_friendly&gt;<span class="tag-attr">yes</span>&lt;/video:family_friendly&gt;   
         &lt;video:requires_subscription&gt;<span class="tag-attr">no</span>&lt;/video:requires_subscription&gt;
         &lt;video:uploader <span class="tag">info</span>="<span class="tag-attr">https://www.youtube.com/user/basj1976</span>"&gt;<span class="tag-attr">basi1976</span>&lt;/video:uploader&gt;
         &lt;video:live&gt;<span class="tag-attr">yes</span>&lt;/video:live&gt;
      &lt;/video:video&gt;      
   &lt;/url&gt;
&lt;/urlset&gt; 
</code></pre>
<blockquote>
<p class="note">All HTML entities in the title, or description should be escaped or wrapped in a <a href="https://en.wikipedia.org/wiki/CDATA" target="_blank" rel="tag nofollow noopener">CDATA</a> block.</p>
</blockquote>
&nbsp;