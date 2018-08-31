---
ID: 342
post_title: >
  How to Create a Schema.org
  AccountingService Markup
author: iurianu
post_excerpt: ""
layout: post
permalink: >
  https://purls.site/semantic-markup/schema-org/how-to-create-a-schema-org-accountingservice-markup/
published: true
post_date: 2017-03-21 14:40:16
---
The following article presents the steps in creating the markup for an Accounting Service, based on a live website information. I will not use all the info on the website, but only some of it, in order to provide a complete, and correct markup, so it can be easily understood by anyone.
As I didn't have access to the HTML code, I created an ld+json script that covers the info from the home page.

As defined by schema.org, this declares the type for an Accountancy business, as a LocalBusiness that can be described as a provider of one or more Service(s).

On the official schema.org website, the breadcrumb list for this particular type is defined as follows:
<ul><li>Thing &gt; Organization &gt; LocalBusiness &gt; FinancialService &gt; AccountingService</li><li>Thing &gt; Place &gt; LocalBusiness &gt; FinancialService &gt; AccountingService</li></ul>
<pre><p>
&lt;script type="application/ld+json"&gt;
// &lt;![CDATA[
{
	"@context": "https://schema.org/",
	"@type": "AccountingService",
	"name": "Leenane Templeton Accountants",
	"url": "https://leenanetempleton.com.au",
	"sameAs": [
		"https://www.facebook.com/leenane.templeton",
		"https://plus.google.com/u/0/110256648224896063412/about",
		"https://www.linkedin.com/company/leenane-templeton-chartered-accountants-&amp;-business-advisors",
		"https://twitter.com/leenanes",
		"https://www.youtube.com/channel/UC1iK_eTl0j-XsYXNZUNm25Q",
		"https://flipboard.com/@leenanetemp49qt"
	],
	"image": "http://leenanetempleton.com.au/wp-content/uploads/2015/11/Newcastle-Accountants-logo-Col.png",
	"address": {
		"@type": "PostalAddress",
		"streetAddress": "134 King Street",
		"addressLocality": "Newcastle",
		"addressRegion": "NSW 2300",
		"addressCountry": "Australia"
	},
	"telephone": "02 4926 2300",
	"faxNumber": "02 4926 2533",
	"email": "success@leenanetempleton.com.au",
	"priceRange": "$$$",
	"makesOffer": {
		"@type": "AggregateOffer",
		"priceSpecification": {
			"@type": "PriceSpecification",
			"priceCurrency": "AUD"
		},
		"eligibleRegion": {
			"@type": "AdministrativeArea",
			"name": "Newcastle, NSW 2300, Australia",
			"hasMap": "https://goo.gl/maps/U1uyf74U3f22"
		},
		"itemOffered": [
			{	"@type": "Service",
				"serviceType": "Tax Accountant",
				"description": "We help to find opportunities that could help reduce your tax, now and in the future.",
				"availableChannel": 
				{	"@type": "ServiceChannel",
					"serviceUrl": "http://leenanetempleton.com.au/accounting/tax-advice-newcastle/"
				}
			},
			{	"@type": "Service",
				"serviceType": "Business Accountants",
				"description": "Specialist business advice to assist in your business needs.",
				"availableChannel": 
				{	"@type": "ServiceChannel",
					"serviceUrl": "https://leenanetempleton.com.au/newcastle/business-advisory/"
				}
			}			
		]
	},
	"potentialAction": {
		"@type": "InteractAction",
		"description": "We're Ready To Answer Your Questions Now."
	}
}
// ]]&gt;
&lt;/script&gt;
</p></pre>