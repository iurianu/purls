---
ID: 397
post_title: How to Create a Local Business Markup
author: iurianu
post_excerpt: ""
layout: post
permalink: >
  https://purls.site/semantic-markup/schema-org/how-to-create-a-local-business-markup/
published: true
post_date: 2017-03-28 12:57:38
---
<p>Providing business information to Google, and other Search Engines is straightforward: simply define a schema.org LocalBusiness item for each business location, inclusive of: disambiguation properties such as the business name, address, and telephone, and service-related properties such as operating hours and menu URLs.</p>



<p>Google recommends using the JSON-LD format to add this information to the page, and for the home page or registration page of the business' official website to contain a schema.org markup block that:
<ul>
<li>disambiguates the business;</li>
<li>contains deeplinks to the web/mobile app form on which the user can complete the action.</li></ul>
<p>Within the Schema.org vocabulary, <em>Local Business</em> inherits properties from both <em>Place</em> and <em>Organization</em> classes.</p>
<p>In this article, I will cover the creation of a <em>Local Business</em> complete Structured Data Markup, in all JSON-LD, microdata, and RDFa versions, using only Schema.org.</p>

<h5>JSON-LD</h5>
<pre>
<code>
<span class="pre-tag">&lt;script</span> <span class="pre-attr">type</span>="<span class="pre-val">application/ld+json</span>"<span class="pre-tag">&gt;</span>
<span class="pre-tag">{</span>
"<span class="pre-attr">@context</span>" : "<span class="pre-val">http://schema.org</span>",
	"<span class="pre-attr">@type</span>" : "<span class="pre-val">LocalBusiness</span>",
	"<span class="pre-val">name</span>" : "kazenokodomo",
	"<span class="pre-val">foundingDate</span>" : "2014",
	"<span class="pre-val">foundingLocation</span>" : "Iaşi, România",
	"<span class="pre-val">brand</span>" : "kazenokodomo",
	"<span class="pre-val">legalName</span>" : "S.C. Kazenokodomo S.R.L.",
	"<span class="pre-val">logo</span>" : "http://kazenokodomo.tech/wp-content/uploads/2016/04/cropped-logo512.png",
	"<span class="pre-val">contactPoint</span>" : <span class="pre-tag">{</span>
		"<span class="pre-attr">@type</span>" : "<span class="pre-val">ContactPoint</span>",
		"<span class="pre-val">contactType</span>" : "customer support",
		"<span class="pre-val">url</span>" : "http://kazenokodomo.tech",
		"<span class="pre-val">email</span>" : "kazenokodomo@mail.com",
		"<span class="pre-val">telephone</span>" : "+40.729.062.628",
		"<span class="pre-val">areaServed</span>" : <span class="pre-tag">[</span>"RO",
            <span class="pre-tag">{</span>
            "<span class="pre-attr">@type</span>": "<span class="pre-val">Place</span>",
		"<span class="pre-val">geo</span>":<span class="pre-tag">{</span>
	  		"<span class="pre-attr">@type</span>": "<span class="pre-val">GeoCoordinates</span>",
			"<span class="pre-val">latitude</span>": "47.148630",
			"<span class="pre-val">longitude</span>": "27.607529"
			<span class="pre-tag">}</span>
        <span class="pre-tag">}</span>
        <span class="pre-tag">]</span>,
		"<span class="pre-val">productSupported</span>" : <span class="pre-tag">[</span>"Search Engine Optimization", "Structured Data Markup", "HTML Semantic Markup"<span class="pre-tag">]</span>,
		"<span class="pre-val">availableLanguage</span>" : <span class="pre-tag">[</span>"Romanian", "English", "French"<span class="pre-tag">]</span>
	<span class="pre-tag">}</span>,
	"<span class="pre-val">aggregateRating</span>": <span class="pre-tag">{</span>
		"<span class="pre-attr">@type</span>": "<span class="pre-val">AggregateRating</span>",
		"<span class="pre-val">bestRating</span>": "5",
		"<span class="pre-val">ratingCount</span>": "162",
		"<span class="pre-val">ratingValue</span>": "5"
	<span class="pre-tag">}</span>,
	"<span class="pre-val">address</span>" : <span class="pre-tag">{</span>
		"<span class="pre-attr">@type</span>": "<span class="pre-val">PostalAddress</span>",
		"<span class="pre-val">addressLocality</span>": "Iaşi",
		"<span class="pre-val">addressRegion</span>": "Iaşi",
		"<span class="pre-val">addressCountry</span>": "România",
		"<span class="pre-val">streetAddress</span>": "Vasile Lupu, Nr. 93",
		"<span class="pre-val">postalCode</span>": "700319"
	<span class="pre-tag">}</span>,        
	"<span class="pre-val">numberOfEmployees</span>" : "1-10",
	"<span class="pre-val">member</span>": <span class="pre-tag">{</span>
		"<span class="pre-attr">@type</span>": "<span class="pre-val">OrganizationRole</span>",
		"<span class="pre-val">member</span>": <span class="pre-tag">{</span>
			"<span class="pre-attr">@type</span>": "<span class="pre-val">Person</span>",
			"<span class="pre-val">name</span>": "Iulian Andriescu"			
		<span class="pre-tag">}</span>,		  
		"<span class="pre-val">startDate</span>": "2014",
		"<span class="pre-val">endDate</span>": "N/A",
		"<span class="pre-val">roleName</span>": "CEO"
	<span class="pre-tag">}</span>,
	"<span class="pre-val">founders</span>" : <span class="pre-tag">[</span>"Cornel Andriescu" , "Iulian Andriescu"<span class="pre-tag">]</span>,
	"<span class="pre-val">url</span>" : "http://kazenokodomo.tech",
	"<span class="pre-val">sameAs</span>" : <span class="pre-tag">[</span>
	"https://plus.google.com/+KazenokodomoWebsite/",
	"https://www.linkedin.com/company/kazenokodomo",
	"https://www.facebook.com/kazenokodomo.iasi/"
	<span class="pre-tag">]	</span>
<span class="pre-tag">}</span>
<span class="pre-tag">&lt;/script&gt;</span>
</code>
</pre>

<h5>Microdata</h5>
<pre>
<code>
<span class="pre-tag">&lt;dl</span> <span class="pre-attr">itemscope</span> <span class="pre-attr">itemtype</span>="<span class="pre-val">http://schema.org/LocalBusiness</span>"<span class="pre-tag">&gt;</span>
	<span class="pre-tag">&lt;dt&gt;</span>Company Name<span class="pre-tag">&lt;/dt&gt;</span> <span class="pre-tag">&lt;dd</span> <span class="pre-attr">itemprop</span>="<span class="pre-val">name</span>"<span class="pre-tag">&gt;</span>kazenokodomo<span class="pre-tag">&lt;/dd&gt;</span>
	<span class="pre-tag">&lt;dt&gt;</span>Founding Date<span class="pre-tag">&lt;/dt&gt;</span> <span class="pre-tag">&lt;dd</span> <span class="pre-attr">itemprop</span>="<span class="pre-val">foundingDate</span>"<span class="pre-tag">&gt;</span>2014<span class="pre-tag">&lt;/dd&gt;</span>
	<span class="pre-tag">&lt;dt&gt;</span>Founding Location<span class="pre-tag">&lt;/dt&gt;</span> <span class="pre-tag">&lt;dd</span> <span class="pre-attr">itemprop</span>="<span class="pre-val">foundingLocation</span>"<span class="pre-tag">&gt;</span>Iaşi, România<span class="pre-tag">&lt;/dd&gt;</span>
	<span class="pre-tag">&lt;dt&gt;</span>Brand Name<span class="pre-tag">&lt;/dt&gt;</span><span class="pre-tag">&lt;dd</span> <span class="pre-attr">itemprop</span>="<span class="pre-val">brand</span>"<span class="pre-tag">&gt;</span>kazenokodomo<span class="pre-tag">&lt;/dd&gt;</span>
	<span class="pre-tag">&lt;dt&gt;</span>Legal Name<span class="pre-tag">&lt;/dt&gt;</span><span class="pre-tag">&lt;dd</span> <span class="pre-attr">itemprop</span>="<span class="pre-val">legalName</span>"<span class="pre-tag">&gt;</span>S.C. Kazenokodomo S.R.L.<span class="pre-tag">&lt;/dd&gt;</span>
	<span class="pre-tag">&lt;dt&gt;</span>URL<span class="pre-tag">&lt;/dt&gt;</span><span class="pre-tag">&lt;dd&gt;</span><span class="pre-tag">&lt;a</span> <span class="pre-attr">itemprop</span>="<span class="pre-val">url</span>" <span class="pre-attr">href</span>="http://kazenokodomo.tech"<span class="pre-tag">&gt;</span>http://kazenokodomo.tech<span class="pre-tag">&lt;/a&gt;</span><span class="pre-tag">&lt;/dd&gt;</span>
	<span class="pre-tag">&lt;dt&gt;</span>Google Plus<span class="pre-tag">&lt;/dt&gt;</span><span class="pre-tag">&lt;dd&gt;</span><span class="pre-tag">&lt;a</span> <span class="pre-attr">itemprop</span>="<span class="pre-val">sameAs</span>" <span class="pre-attr">href</span>="https://plus.google.com/+KazenokodomoWebsite/"<span class="pre-tag">&gt;</span>https://plus.google.com/+KazenokodomoWebsite/<span class="pre-tag">&lt;/a&gt;</span><span class="pre-tag">&lt;/dd&gt;</span>
	<span class="pre-tag">&lt;dt&gt;</span>Linkedin<span class="pre-tag">&lt;/dt&gt;</span><span class="pre-tag">&lt;dd&gt;</span><span class="pre-tag">&lt;a</span> <span class="pre-attr">itemprop</span>="<span class="pre-val">sameAs</span>" <span class="pre-attr">href</span>="https://www.linkedin.com/company/kazenokodomo"<span class="pre-tag">&gt;</span>https://www.linkedin.com/company/kazenokodomo<span class="pre-tag">&lt;/a&gt;</span><span class="pre-tag">&lt;/dd&gt;</span>
	<span class="pre-tag">&lt;dt&gt;</span>Facebook<span class="pre-tag">&lt;/dt&gt;</span><span class="pre-tag">&lt;dd&gt;</span><span class="pre-tag">&lt;a</span> <span class="pre-attr">itemprop</span>="<span class="pre-val">sameAs</span>" <span class="pre-attr">href</span>="https://www.facebook.com/kazenokodomo.iasi/"<span class="pre-tag">&gt;</span>https://www.facebook.com/kazenokodomo.iasi/<span class="pre-tag">&lt;/a&gt;</span><span class="pre-tag">&lt;/dd&gt;</span>
	<span class="pre-tag">&lt;dt&gt;</span>Logo<span class="pre-tag">&lt;/dt&gt;</span>
		<span class="pre-tag">&lt;dd</span> <span class="pre-attr">itemprop</span>="<span class="pre-val">logo</span>" <span class="pre-attr">itemscope</span> <span class="pre-attr">itemtype</span>="<span class="pre-val">http://schema.org/ImageObject</span>"<span class="pre-tag">&gt;</span>
			<span class="pre-tag">&lt;a</span> <span class="pre-attr">itemprop</span>="<span class="pre-val">url</span>" <span class="pre-attr">href</span>="http://kazenokodomo.tech"<span class="pre-tag">&gt;</span>
				<span class="pre-tag">&lt;img</span> <span class="pre-attr">itemprop</span>="<span class="pre-val">image</span>" <span class="pre-attr">src</span>="http://kazenokodomo.tech/wp-content/uploads/2016/04/cropped-logo512.png" style="width:30px;margin-top:-35px" <span class="pre-tag">/&gt;</span>
			<span class="pre-tag">&lt;/a&gt;</span>
		<span class="pre-tag">&lt;/dd&gt;</span>
	<span class="pre-tag">&lt;dt&gt;</span>CEO<span class="pre-tag">&lt;/dt&gt;</span>
		<span class="pre-tag">&lt;dd</span> <span class="pre-attr">itemprop</span>="<span class="pre-val">member</span>" <span class="pre-attr">itemscope</span> <span class="pre-attr">itemtype</span>="<span class="pre-val">http://schema.org/OrganizationRole</span>"<span class="pre-tag">/&gt;</span>
			<span class="pre-tag">&lt;ul&gt;</span>
				<span class="pre-tag">&lt;li</span> <span class="pre-attr">itemprop</span>="<span class="pre-val">member</span>" <span class="pre-attr">itemscope</span> <span class="pre-attr">itemtype</span>="<span class="pre-val">http://schema.org/Person</span>"<span class="pre-tag">&gt;</span>
					Name: <span class="pre-tag">&lt;em</span> <span class="pre-attr">itemprop</span>="<span class="pre-val">name</span>"<span class="pre-tag">&gt;</span>Iulian Andriescu<span class="pre-tag">&lt;/em&gt;</span>
				<span class="pre-tag">&lt;/li&gt;</span>
				<span class="pre-tag">&lt;li&gt;</span>Start Date: <span class="pre-tag">&lt;span</span> <span class="pre-attr">itemprop</span>="<span class="pre-val">startDate</span>"<span class="pre-tag">&gt;</span>2014<span class="pre-tag">&lt;/span&gt;</span><span class="pre-tag">&lt;/li&gt;</span>
				<span class="pre-tag">&lt;li&gt;</span>End Date: <span class="pre-tag">&lt;span</span> <span class="pre-attr">itemprop</span>="<span class="pre-val">endDate</span>"<span class="pre-tag">&gt;</span>N/A<span class="pre-tag">&lt;/span&gt;</span><span class="pre-tag">&lt;/li&gt;</span>
				<span class="pre-tag">&lt;li&gt;</span>Role Name: <span class="pre-tag">&lt;span</span> <span class="pre-attr">itemprop</span>="<span class="pre-val">roleName</span>"<span class="pre-tag">&gt;</span>CEO<span class="pre-tag">&lt;/span&gt;</span><span class="pre-tag">&lt;/li&gt;</span>
			<span class="pre-tag">&lt;/ul&gt;</span>
		<span class="pre-tag">&lt;/dd&gt;</span>
	<span class="pre-tag">&lt;dt&gt;</span>Founders<span class="pre-tag">&lt;/dt&gt;</span>
		<span class="pre-tag">&lt;dd&gt;</span>
			<span class="pre-tag">&lt;ul&gt;</span>			
				<span class="pre-tag">&lt;li</span> <span class="pre-attr">itemprop</span>="<span class="pre-val">founder</span>" <span class="pre-attr">itemscope</span> <span class="pre-attr">itemtype</span>="<span class="pre-val">http://schema.org/Person</span>"<span class="pre-tag">&gt;</span><span class="pre-tag">&lt;span</span> <span class="pre-attr">itemprop</span>="<span class="pre-val">name</span>"<span class="pre-tag">&gt;</span>Cornel Andriescu<span class="pre-tag">&lt;/span&gt;</span><span class="pre-tag">&lt;/li&gt;</span>
				<span class="pre-tag">&lt;li</span> <span class="pre-attr">itemprop</span>="<span class="pre-val">founder</span>" <span class="pre-attr">itemscope</span> <span class="pre-attr">itemtype</span>="<span class="pre-val">http://schema.org/Person</span>"<span class="pre-tag">&gt;</span><span class="pre-tag">&lt;span</span> <span class="pre-attr">itemprop</span>="<span class="pre-val">name</span><span class="pre-tag">&gt;</span>Iulian Andriescu<span class="pre-tag">&lt;/span&gt;</span><span class="pre-tag">&lt;/li&gt;</span>
			<span class="pre-tag">&lt;/ul&gt;</span>
		<span class="pre-tag">&lt;/dd&gt;</span>		
	<span class="pre-tag">&lt;dt&gt;</span>Address:<span class="pre-tag">&lt;/dt&gt;</span>
		<span class="pre-tag">&lt;dd</span> <span class="pre-attr">itemprop</span>="<span class="pre-val">address</span>" <span class="pre-attr">itemscope</span> <span class="pre-attr">itemtype</span>="<span class="pre-val">http://schema.org/PostalAddress</span>"<span class="pre-tag">&gt;</span>
			<span class="pre-tag">&lt;ul&gt;</span>
				<span class="pre-tag">&lt;li&gt;</span>Locality: <span class="pre-tag">&lt;span</span> <span class="pre-attr">itemprop</span>="<span class="pre-val">addressLocality</span>"<span class="pre-tag">&gt;</span>Iaşi<span class="pre-tag">&lt;/span&gt;</span><span class="pre-tag">&lt;/li&gt;</span>
				<span class="pre-tag">&lt;li&gt;</span>Street Address: <span class="pre-tag">&lt;span</span> <span class="pre-attr">itemprop</span>="<span class="pre-val">streetAddress</span>"<span class="pre-tag">&gt;</span>Vasile Lupu, Nr. 93<span class="pre-tag">&lt;/span&gt;</span><span class="pre-tag">&lt;/li&gt;</span>
				<span class="pre-tag">&lt;li&gt;</span>Postal Code: <span class="pre-tag">&lt;span</span> <span class="pre-attr">itemprop</span>="<span class="pre-val">postalCode</span>"<span class="pre-tag">&gt;</span>700319<span class="pre-tag">&lt;/span&gt;</span><span class="pre-tag">&lt;/li&gt;</span>
				<span class="pre-tag">&lt;li&gt;</span>Region: <span class="pre-tag">&lt;span</span> <span class="pre-attr">itemprop</span>="<span class="pre-val">addressRegion</span>"<span class="pre-tag">&gt;</span>Iaşi<span class="pre-tag">&lt;/span&gt;</span><span class="pre-tag">&lt;/li&gt;</span>
				<span class="pre-tag">&lt;li&gt;</span>Country: <span class="pre-tag">&lt;span</span> <span class="pre-attr">itemprop</span>="<span class="pre-val">addressCountry</span>"<span class="pre-tag">&gt;</span>România<span class="pre-tag">&lt;/span&gt;</span><span class="pre-tag">&lt;/li&gt;</span>
			<span class="pre-tag">&lt;/ul&gt;</span>
		<span class="pre-tag">&lt;/dd&gt;</span>  
	<span class="pre-tag">&lt;dt&gt;</span>Contact Point<span class="pre-tag">&lt;/dt&gt;</span>
		<span class="pre-tag">&lt;dd</span> <span class="pre-attr">itemprop</span>="<span class="pre-val">contactPoint</span>" <span class="pre-attr">itemscope</span> <span class="pre-attr">itemtype</span>="<span class="pre-val">http://schema.org/ContactPoint</span>"<span class="pre-tag">&gt;</span>
			<span class="pre-tag">&lt;ul&gt;</span>
				<span class="pre-tag">&lt;li&gt;</span>ContactType: <span class="pre-tag">&lt;span</span> <span class="pre-attr">itemprop</span>="<span class="pre-val">contactType</span>"<span class="pre-tag">&gt;</span>customer support<span class="pre-tag">&lt;/span&gt;&lt;/li&gt;</span>
				<span class="pre-tag">&lt;li&gt;</span>URL: <span class="pre-tag">&lt;a</span> <span class="pre-attr">itemprop</span>="<span class="pre-val">url</span>" <span class="pre-attr">href</span>="http://kazenokodomo.tech"<span class="pre-tag">&gt;</span>http://kazenokodomo.tech<span class="pre-tag">&lt;/a&gt;&lt;/li&gt;</span>
				<span class="pre-tag">&lt;li&gt;</span>Email: <span class="pre-tag">&lt;span</span> <span class="pre-attr">itemprop</span>="<span class="pre-val">email</span>"<span class="pre-tag">&gt;</span>kazenokodomo@mail.com<span class="pre-tag">&lt;/span&gt;&lt;/li&gt;</span>
				<span class="pre-tag">&lt;li&gt;</span>Phone: <span class="pre-tag">&lt;span</span> <span class="pre-attr">itemprop</span>="<span class="pre-val">telephone</span>"<span class="pre-tag">&gt;</span>+40.729.062.628<span class="pre-tag">&lt;/span&gt;&lt;/li&gt;</span>
				<span class="pre-tag">&lt;li&gt;</span>Area Served: 
					<span class="pre-tag">&lt;meta</span> <span class="pre-attr">itemprop</span>="<span class="pre-val">areaServed</span>" <span class="pre-attr">content</span>="RO"<span class="pre-tag">/&gt;</span>
					<span class="pre-tag">&lt;span</span> <span class="pre-attr">itemprop</span>="<span class="pre-val">areaServed</span>" <span class="pre-attr">itemscope</span> <span class="pre-attr">itemtype</span>="<span class="pre-val">http://schema.org/Place</span>"<span class="pre-tag">&gt;</span>
						<span class="pre-tag">&lt;em</span> <span class="pre-attr">itemprop</span>="<span class="pre-val">geo</span>" <span class="pre-attr">itemscope</span> <span class="pre-attr">itemtype</span>="<span class="pre-val">http://schema.org/GeoCoordinates</span>"<span class="pre-tag">&gt;</span>
							<span class="pre-tag">&lt;meta</span> <span class="pre-attr">itemprop</span>="<span class="pre-val">latitude</span>" <span class="pre-attr">content</span>="47.148630" <span class="pre-tag">/&gt;</span>
							<span class="pre-tag">&lt;meta</span> <span class="pre-attr">itemprop</span>="<span class="pre-val">longitude</span>" <span class="pre-attr">content</span>="27.607529" <span class="pre-tag">/&gt;</span>
						<span class="pre-tag">&lt;/em&gt;</span>
					<span class="pre-tag">&lt;/span&gt;</span>
				<span class="pre-tag">&lt;/li&gt;</span>
				<span class="pre-tag">&lt;li&gt;</span>Supported Products:
					<span class="pre-tag">&lt;ul&gt;</span>
						<span class="pre-tag">&lt;li</span> <span class="pre-attr">itemprop</span>="<span class="pre-val">productSupported</span>"<span class="pre-tag">&gt;</span>Search Engine Optimization<span class="pre-tag">&lt;/li&gt;</span>
						<span class="pre-tag">&lt;li</span> <span class="pre-attr">itemprop</span>="<span class="pre-val">productSupported</span>"<span class="pre-tag">&gt;</span>Structured Data Markup<span class="pre-tag">&lt;/li&gt;</span>
						<span class="pre-tag">&lt;li</span> <span class="pre-attr">itemprop</span>="<span class="pre-val">productSupported</span>"<span class="pre-tag">&gt;</span>HTML Semantic Markup"<span class="pre-tag">&lt;/li&gt;</span>
					<span class="pre-tag">&lt;/ul&gt;</span>
				<span class="pre-tag">&lt;/li&gt;</span>
				<span class="pre-tag">&lt;li&gt;</span>Available Languages:
					<span class="pre-tag">&lt;ul&gt;</span>
						<span class="pre-tag">&lt;li</span> <span class="pre-attr">itemprop</span>="<span class="pre-val">availableLanguage</span>"<span class="pre-tag">&gt;</span>Romanian<span class="pre-tag">&lt;/li&gt;</span>
						<span class="pre-tag">&lt;li</span> <span class="pre-attr">itemprop</span>="<span class="pre-val">availableLanguage</span>"<span class="pre-tag">&gt;</span>English<span class="pre-tag">&lt;/li&gt;</span>
						<span class="pre-tag">&lt;li</span> <span class="pre-attr">itemprop</span>="<span class="pre-val">availableLanguage</span>"<span class="pre-tag">&gt;</span>French<span class="pre-tag">&lt;/li&gt;</span>
					<span class="pre-tag">&lt;/ul&gt;</span>
				<span class="pre-tag">&lt;/li&gt;</span>
			<span class="pre-tag">&lt;/ul&gt;</span>
		<span class="pre-tag">&lt;/dd&gt;</span>
	<span class="pre-tag">&lt;dt&gt;</span>Aggregate Rating<span class="pre-tag">&lt;/dt&gt;</span>
		<span class="pre-tag">&lt;dd</span> <span class="pre-attr">itemprop</span>="<span class="pre-val">aggregateRating</span>" <span class="pre-attr">itemscope</span> <span class="pre-attr">itemtype</span>="<span class="pre-val">http://schema.org/AggregateRating</span>"<span class="pre-tag">&gt;</span>Rated 
			<span class="pre-tag">&lt;span</span> <span class="pre-attr">itemprop</span>="<span class="pre-val">ratingValue</span>"<span class="pre-tag">&gt;</span>5<span class="pre-tag">&lt;/span&gt;</span> out of 
			<span class="pre-tag">&lt;span</span> <span class="pre-attr">itemprop</span>="<span class="pre-val">bestRating</span>"<span class="pre-tag">&gt;</span>5<span class="pre-tag">&lt;/span&gt;</span> from 
			<span class="pre-tag">&lt;span</span> <span class="pre-attr">itemprop</span>="<span class="pre-val">reviewCount</span>"<span class="pre-tag">&gt;</span>162<span class="pre-tag">&lt;/span&gt;</span> reviews.
		<span class="pre-tag">&lt;/dd&gt;</span> 
	<span class="pre-tag">&lt;dt&gt;</span>Number of Employees<span class="pre-tag">&lt;/dt&gt;</span> <span class="pre-tag">&lt;dd</span> <span class="pre-attr">itemprop</span>="<span class="pre-val">numberOfEmployees</span>"<span class="pre-tag">&gt;</span>1-10<span class="pre-tag">&lt;/dd&gt;</span>		
<span class="pre-tag">&lt;/dl&gt;</span>
</code>
</pre>

<h5>RDFa</h5>
<pre>
<code>
<span class="pre-tag">&lt;dl</span> <span class="pre-attr">vocab</span>="<span class="pre-val">http://schema.org/</span>" <span class="pre-attr">typeof</span>="<span class="pre-val">LocalBusiness</span>"<span class="pre-tag">&gt;</span>
	<span class="pre-tag">&lt;dt&gt;</span>Company Name<span class="pre-tag">&lt;/dt&gt;</span> <span class="pre-tag">&lt;dd</span> <span class="pre-attr">property</span>="<span class="pre-val">name</span>"<span class="pre-tag">&gt;</span>kazenokodomo<span class="pre-tag">&lt;/dd&gt;</span>
	<span class="pre-tag">&lt;dt&gt;</span>Founding Date<span class="pre-tag">&lt;/dt&gt;</span> <span class="pre-tag">&lt;dd</span> <span class="pre-attr">property</span>="<span class="pre-val">foundingDate</span>"<span class="pre-tag">&gt;</span>2014<span class="pre-tag">&lt;/dd&gt;</span>
	<span class="pre-tag">&lt;dt&gt;</span>Founding Location<span class="pre-tag">&lt;/dt&gt;</span> <span class="pre-tag">&lt;dd</span> <span class="pre-attr">property</span>="<span class="pre-val">foundingLocation</span>"<span class="pre-tag">&gt;</span>Iaşi, România<span class="pre-tag">&lt;/dd&gt;</span>
	<span class="pre-tag">&lt;dt&gt;</span>Brand Name<span class="pre-tag">&lt;/dt&gt;</span><span class="pre-tag">&lt;dd</span> <span class="pre-attr">property</span>="<span class="pre-val">brand</span>"<span class="pre-tag">&gt;</span>kazenokodomo<span class="pre-tag">&lt;/dd&gt;</span>
	<span class="pre-tag">&lt;dt&gt;</span>Legal Name<span class="pre-tag">&lt;/dt&gt;</span><span class="pre-tag">&lt;dd</span> <span class="pre-attr">property</span>="<span class="pre-val">legalName</span>"<span class="pre-tag">&gt;</span>S.C. Kazenokodomo S.R.L.<span class="pre-tag">&lt;/dd&gt;</span>
	<span class="pre-tag">&lt;dt&gt;</span>URL<span class="pre-tag">&lt;/dt&gt;</span><span class="pre-tag">&lt;dd&gt;</span><span class="pre-tag">&lt;a</span> <span class="pre-attr">property</span>="<span class="pre-val">url</span>" <span class="pre-attr">href</span>="http://kazenokodomo.tech"<span class="pre-tag">&gt;</span>http://kazenokodomo.tech<span class="pre-tag">&lt;/a&gt;</span><span class="pre-tag">&lt;/dd&gt;</span>
	<span class="pre-tag">&lt;dt&gt;</span>Google Plus<span class="pre-tag">&lt;/dt&gt;</span><span class="pre-tag">&lt;dd&gt;</span><span class="pre-tag">&lt;a</span> <span class="pre-attr">property</span>="<span class="pre-val">sameAs</span>" <span class="pre-attr">href</span>="https://plus.google.com/+KazenokodomoWebsite/"<span class="pre-tag">&gt;</span>https://plus.google.com/+KazenokodomoWebsite/<span class="pre-tag">&lt;/a&gt;</span><span class="pre-tag">&lt;/dd&gt;</span>
	<span class="pre-tag">&lt;dt&gt;</span>Linkedin<span class="pre-tag">&lt;/dt&gt;</span><span class="pre-tag">&lt;dd&gt;</span><span class="pre-tag">&lt;a</span> <span class="pre-attr">property</span>="<span class="pre-val">sameAs</span>" <span class="pre-attr">href</span>="https://www.linkedin.com/company/kazenokodomo"<span class="pre-tag">&gt;</span>https://www.linkedin.com/company/kazenokodomo<span class="pre-tag">&lt;/a&gt;</span><span class="pre-tag">&lt;/dd&gt;</span>
	<span class="pre-tag">&lt;dt&gt;</span>Facebook<span class="pre-tag">&lt;/dt&gt;</span><span class="pre-tag">&lt;dd&gt;</span><span class="pre-tag">&lt;a</span> <span class="pre-attr">property</span>="<span class="pre-val">sameAs</span>" <span class="pre-attr">href</span>="https://www.facebook.com/kazenokodomo.iasi/"<span class="pre-tag">&gt;</span>https://www.facebook.com/kazenokodomo.iasi/<span class="pre-tag">&lt;/a&gt;</span><span class="pre-tag">&lt;/dd&gt;</span>
	<span class="pre-tag">&lt;dt&gt;</span>Logo<span class="pre-tag">&lt;/dt&gt;</span>
		<span class="pre-tag">&lt;dd</span> <span class="pre-attr">property</span>="<span class="pre-val">logo</span>" <span class="pre-attr">typeof</span>="<span class="pre-val">ImageObject</span>"<span class="pre-tag">&gt;</span>
			<span class="pre-tag">&lt;a</span> <span class="pre-attr">property</span>="<span class="pre-val">url</span>" <span class="pre-attr">href</span>="http://kazenokodomo.tech"<span class="pre-tag">&gt;</span>
				<span class="pre-tag">&lt;img</span> <span class="pre-attr">property</span>="<span class="pre-val">image</span>" <span class="pre-attr">src</span>="http://kazenokodomo.tech/wp-content/uploads/2016/04/cropped-logo512.png" style="width:30px;margin-top:-35px" <span class="pre-tag">/&gt;</span>
			<span class="pre-tag">&lt;/a&gt;</span>
		<span class="pre-tag">&lt;/dd&gt;</span>
	<span class="pre-tag">&lt;dt&gt;</span>CEO<span class="pre-tag">&lt;/dt&gt;</span>
		<span class="pre-tag">&lt;dd</span> <span class="pre-attr">property</span>="<span class="pre-val">member</span>" <span class="pre-attr">typeof</span>="<span class="pre-val">OrganizationRole</span>"<span class="pre-tag">/&gt;</span>
			<span class="pre-tag">&lt;ul&gt;</span>
				<span class="pre-tag">&lt;li</span> <span class="pre-attr">property</span>="<span class="pre-val">member</span>" <span class="pre-attr">typeof</span>="<span class="pre-val">Person</span>"<span class="pre-tag">&gt;</span>
					Name: <span class="pre-tag">&lt;em</span> <span class="pre-attr">property</span>="<span class="pre-val">name</span>"<span class="pre-tag">&gt;</span>Iulian Andriescu<span class="pre-tag">&lt;/em&gt;</span>
				<span class="pre-tag">&lt;/li&gt;</span>
				<span class="pre-tag">&lt;li&gt;</span>Start Date: <span class="pre-tag">&lt;span</span> <span class="pre-attr">property</span>="<span class="pre-val">startDate</span>"<span class="pre-tag">&gt;</span>2014<span class="pre-tag">&lt;/span&gt;</span><span class="pre-tag">&lt;/li&gt;</span>
				<span class="pre-tag">&lt;li&gt;</span>End Date: <span class="pre-tag">&lt;span</span> <span class="pre-attr">property</span>="<span class="pre-val">endDate</span>"<span class="pre-tag">&gt;</span>N/A<span class="pre-tag">&lt;/span&gt;</span><span class="pre-tag">&lt;/li&gt;</span>
				<span class="pre-tag">&lt;li&gt;</span>Role Name: <span class="pre-tag">&lt;span</span> <span class="pre-attr">property</span>="<span class="pre-val">roleName</span>"<span class="pre-tag">&gt;</span>CEO<span class="pre-tag">&lt;/span&gt;</span><span class="pre-tag">&lt;/li&gt;</span>
			<span class="pre-tag">&lt;/ul&gt;</span>
		<span class="pre-tag">&lt;/dd&gt;</span>
	<span class="pre-tag">&lt;dt&gt;</span>Founders<span class="pre-tag">&lt;/dt&gt;</span>
		<span class="pre-tag">&lt;dd&gt;</span>
			<span class="pre-tag">&lt;ul&gt;</span>			
				<span class="pre-tag">&lt;li</span> <span class="pre-attr">property</span>="<span class="pre-val">founder</span>" <span class="pre-attr">typeof</span>="<span class="pre-val">Person</span>"<span class="pre-tag">&gt;</span><span class="pre-tag">&lt;span</span> <span class="pre-attr">property</span>="<span class="pre-val">name</span>"<span class="pre-tag">&gt;</span>Cornel Andriescu<span class="pre-tag">&lt;/span&gt;</span><span class="pre-tag">&lt;/li&gt;</span>
				<span class="pre-tag">&lt;li</span> <span class="pre-attr">property</span>="<span class="pre-val">founder</span>" <span class="pre-attr">typeof</span>="<span class="pre-val">Person</span>"<span class="pre-tag">&gt;</span><span class="pre-tag">&lt;span</span> <span class="pre-attr">property</span>="<span class="pre-val">name</span>"<span class="pre-tag">&gt;</span>Iulian Andriescu<span class="pre-tag">&lt;/span&gt;</span><span class="pre-tag">&lt;/li&gt;</span>
			<span class="pre-tag">&lt;/ul&gt;</span>
		<span class="pre-tag">&lt;/dd&gt;</span>		
	<span class="pre-tag">&lt;dt&gt;</span>Address:<span class="pre-tag">&lt;/dt&gt;</span>
		<span class="pre-tag">&lt;dd</span> <span class="pre-attr">property</span>="<span class="pre-val">address</span>" <span class="pre-attr">typeof</span>="<span class="pre-val">PostalAddress</span>"<span class="pre-tag">&gt;</span>
			<span class="pre-tag">&lt;ul&gt;</span>
				<span class="pre-tag">&lt;li&gt;</span>Locality: <span class="pre-tag">&lt;span</span> <span class="pre-attr">property</span>="<span class="pre-val">addressLocality</span>"<span class="pre-tag">&gt;</span>Iaşi<span class="pre-tag">&lt;/span&gt;</span><span class="pre-tag">&lt;/li&gt;</span>
				<span class="pre-tag">&lt;li&gt;</span>Street Address: <span class="pre-tag">&lt;span</span> <span class="pre-attr">property</span>="<span class="pre-val">streetAddress</span>"<span class="pre-tag">&gt;</span>Vasile Lupu, Nr. 93<span class="pre-tag">&lt;/span&gt;</span><span class="pre-tag">&lt;/li&gt;</span>
				<span class="pre-tag">&lt;li&gt;</span>Postal Code: <span class="pre-tag">&lt;span</span> <span class="pre-attr">property</span>="<span class="pre-val">postalCode</span>"<span class="pre-tag">&gt;</span>700319<span class="pre-tag">&lt;/span&gt;</span><span class="pre-tag">&lt;/li&gt;</span>
				<span class="pre-tag">&lt;li&gt;</span>Region: <span class="pre-tag">&lt;span</span> <span class="pre-attr">property</span>="<span class="pre-val">addressRegion</span>"<span class="pre-tag">&gt;</span>Iaşi<span class="pre-tag">&lt;/span&gt;</span><span class="pre-tag">&lt;/li&gt;</span>
				<span class="pre-tag">&lt;li&gt;</span>Country: <span class="pre-tag">&lt;span</span> <span class="pre-attr">property</span>="<span class="pre-val">addressCountry</span>"<span class="pre-tag">&gt;</span>România<span class="pre-tag">&lt;/span&gt;</span><span class="pre-tag">&lt;/li&gt;</span>
			<span class="pre-tag">&lt;/ul&gt;</span>
		<span class="pre-tag">&lt;/dd&gt;</span>  
	<span class="pre-tag">&lt;dt&gt;</span>Contact Point<span class="pre-tag">&lt;/dt&gt;</span>
		<span class="pre-tag">&lt;dd</span> <span class="pre-attr">property</span>="<span class="pre-val">contactPoint</span>" <span class="pre-attr">typeof</span>="<span class="pre-val">ContactPoint</span>"<span class="pre-tag">&gt;</span>
			<span class="pre-tag">&lt;ul&gt;</span>
				<span class="pre-tag">&lt;li&gt;</span>ContactType: <span class="pre-tag">&lt;span</span> <span class="pre-attr">property</span>="<span class="pre-val">contactType</span>"<span class="pre-tag">&gt;</span>customer support<span class="pre-tag">&lt;/span&gt;&lt;/li&gt;</span>
				<span class="pre-tag">&lt;li&gt;</span>URL: <span class="pre-tag">&lt;a</span> <span class="pre-attr">property</span>="<span class="pre-val">url</span>" <span class="pre-attr">href</span>="http://kazenokodomo.tech"<span class="pre-tag">&gt;</span>http://kazenokodomo.tech<span class="pre-tag">&lt;/a&gt;&lt;/li&gt;</span>
				<span class="pre-tag">&lt;li&gt;</span>Email: <span class="pre-tag">&lt;span</span> <span class="pre-attr">property</span>="<span class="pre-val">email</span>"<span class="pre-tag">&gt;</span>kazenokodomo@mail.com<span class="pre-tag">&lt;/span&gt;&lt;/li&gt;</span>
				<span class="pre-tag">&lt;li&gt;</span>Phone: <span class="pre-tag">&lt;span</span> <span class="pre-attr">property</span>="<span class="pre-val">telephone</span>"<span class="pre-tag">&gt;</span>+40.729.062.628<span class="pre-tag">&lt;/span&gt;&lt;/li&gt;</span>
				<span class="pre-tag">&lt;li&gt;</span>Area Served: 
					<span class="pre-tag">&lt;meta</span> <span class="pre-attr">property</span>="<span class="pre-val">areaServed</span>" <span class="pre-attr">content</span>="RO"<span class="pre-tag">/&gt;</span>
					<span class="pre-tag">&lt;span</span> <span class="pre-attr">property</span>="<span class="pre-val">areaServed</span>" <span class="pre-attr"></span> <span class="pre-attr">typeof</span>="Place"<span class="pre-tag">&gt;</span>
						<span class="pre-tag">&lt;em</span> <span class="pre-attr">property</span>="<span class="pre-val">geo</span>" <span class="pre-attr">typeof</span>="<span class="pre-val">GeoCoordinates</span>"<span class="pre-tag">&gt;</span>
							<span class="pre-tag">&lt;meta</span> <span class="pre-attr">property</span>="<span class="pre-val">latitude</span>" <span class="pre-attr">content</span>="47.148630" <span class="pre-tag">/&gt;</span>
							<span class="pre-tag">&lt;meta</span> <span class="pre-attr">property</span>="<span class="pre-val">longitude</span>" <span class="pre-attr">content</span>="27.607529" <span class="pre-tag">/&gt;</span>
						<span class="pre-tag">&lt;/em&gt;</span>
					<span class="pre-tag">&lt;/span&gt;</span>
				<span class="pre-tag">&lt;/li&gt;</span>
				<span class="pre-tag">&lt;li&gt;</span>Supported Products:
					<span class="pre-tag">&lt;ul&gt;</span>
						<span class="pre-tag">&lt;li</span> <span class="pre-attr">property</span>="<span class="pre-val">productSupported</span>"<span class="pre-tag">&gt;</span>Search Engine Optimization<span class="pre-tag">&lt;/li&gt;</span>
						<span class="pre-tag">&lt;li</span> <span class="pre-attr">property</span>="<span class="pre-val">productSupported</span>"<span class="pre-tag">&gt;</span>Structured Data Markup<span class="pre-tag">&lt;/li&gt;</span>
						<span class="pre-tag">&lt;li</span> <span class="pre-attr">property</span>="<span class="pre-val">productSupported</span>"<span class="pre-tag">&gt;</span>HTML Semantic Markup"<span class="pre-tag">&lt;/li&gt;</span>
					<span class="pre-tag">&lt;/ul&gt;</span>
				<span class="pre-tag">&lt;/li&gt;</span>
				<span class="pre-tag">&lt;li&gt;</span>Available Languages:
					<span class="pre-tag">&lt;ul&gt;</span>
						<span class="pre-tag">&lt;li</span> <span class="pre-attr">property</span>="<span class="pre-val">availableLanguage</span>"<span class="pre-tag">&gt;</span>Romanian<span class="pre-tag">&lt;/li&gt;</span>
						<span class="pre-tag">&lt;li</span> <span class="pre-attr">property</span>="<span class="pre-val">availableLanguage</span>"<span class="pre-tag">&gt;</span>English<span class="pre-tag">&lt;/li&gt;</span>
						<span class="pre-tag">&lt;li</span> <span class="pre-attr">property</span>="<span class="pre-val">availableLanguage</span>"<span class="pre-tag">&gt;</span>French<span class="pre-tag">&lt;/li&gt;</span>
					<span class="pre-tag">&lt;/ul&gt;</span>
				<span class="pre-tag">&lt;/li&gt;</span>
			<span class="pre-tag">&lt;/ul&gt;</span>
		<span class="pre-tag">&lt;/dd&gt;</span>
	<span class="pre-tag">&lt;dt&gt;</span>Aggregate Rating<span class="pre-tag">&lt;/dt&gt;</span>
		<span class="pre-tag">&lt;dd</span> <span class="pre-attr">property</span>="<span class="pre-val">aggregateRating</span>" <span class="pre-attr">typeof</span>="<span class="pre-val">AggregateRating</span>"<span class="pre-tag">&gt;</span>Rated 
			<span class="pre-tag">&lt;span</span> <span class="pre-attr">property</span>="<span class="pre-val">ratingValue</span>"<span class="pre-tag">&gt;</span>5<span class="pre-tag">&lt;/span&gt;</span> out of 
			<span class="pre-tag">&lt;span</span> <span class="pre-attr">property</span>="<span class="pre-val">bestRating</span>"<span class="pre-tag">&gt;</span>5<span class="pre-tag">&lt;/span&gt;</span> from 
			<span class="pre-tag">&lt;span</span> <span class="pre-attr">property</span>="<span class="pre-val">reviewCount</span>"<span class="pre-tag">&gt;</span>162<span class="pre-tag">&lt;/span&gt;</span> reviews.
		<span class="pre-tag">&lt;/dd&gt;</span> 
	<span class="pre-tag">&lt;dt&gt;</span>Number of Employees<span class="pre-tag">&lt;/dt&gt;</span> <span class="pre-tag">&lt;dd</span> <span class="pre-attr">property</span>="<span class="pre-val">numberOfEmployees</span>"<span class="pre-tag">&gt;</span>1-10<span class="pre-tag">&lt;/dd&gt;</span>		
<span class="pre-tag">&lt;/dl&gt;</span>
</code>
</pre>

When you check this markup on Google's Structured Data Testing Tool, you get a preview that looks like this:

<figure class="half-image"><a href="http://purls.site/wp-content/uploads/2017/03/ps-ss.png"><img src="http://purls.site/wp-content/uploads/2017/03/ps-ss.png" alt="Google Structured Data Testing Tool Preview" width="238" height="264" class="alignnone size-full wp-image-409" /></a></figure>