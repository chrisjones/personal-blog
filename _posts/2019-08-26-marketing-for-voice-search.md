---
layout: post
cover: whiskey-glencairn.jpg
categories: posts
tags: analytics
---
<br />

<h2>Voice Search and the Distributor</h2>

<b>What is Voice Search?</b>
<p>By now everyone is, or should be, familiar with Voice Search.  Whether you call out "Hey Siri!" or "Hey Alexa!" or "Hey Google!", you've more than likely used voice search in the recent past whether to call a contact in your contact list or ask what the local weather is outside.  Voice Search is simply using your voice and a microphone-enabled Internet device to search the Internet.</p>

<p>I recently came across an unsourced statistic, "as much as 50% of all searches will be voice driven by 2020."  That's astounding.  Here are some tips to start strategically thinking about and preparing to best position your company for voice search:</p>

<p><b>1. Have you implemented Structured Data? </b></p>

<p>Structured Data is a way to tag your website text so that search engines can better classify the content and in turn index the page.  For example, implementing the Product schema from schema.org for a product:</p>

~~~~~~
<h1 itemprop="name">VICTAULIC® QUICKVIC™ 107N PRE-ASSEMBLED RIGID COUPLING, 4 IN, GROOVE, DUCTILE IRON, 
ORANGE ENAMEL</h1>

<p itemprop="description">Victaulic® QuickVic™ Rigid Coupling, Pre-Assembled, Series: 107N, Coupling, 
4 in Nominal, Groove, 8.39 in Length, 750 psi, Ductile Iron, Orange Enamel, 4-1/2 in OD x 2.04 in W</p>

<p itemprop="brand">Victaulic</p>

<p itemprop="sku">123456789</p>
~~~~~~

<br />
<p>In this example we have clearly identified the product properties name, description, brand, and SKU using the "itemprop" attributes. (Note: the Product schema is actually much longer than the simple example provided.) But with these calls, the search engine knows that this page can be indexed for the brand Victaulic, and assuming the SKU is unique, index for any SKU searches.</p>

<p>Secondly, now the search engines can easily create featured snippets based upon these item properties. Here is an example on the search term "Pneumatics":</p>

![Badge](/images/featured_snippet.png){: .center-image}

<p>In this example, the page title, page URL, and description is provided by structured data on the webpage.  Featured Snippets are cards using that structured data to display the first position of the search results.  That is important because when searching via Voice typically only the first result is communicated to the user.</p>

<p>Homework: research structured data content to help build featured snippets.  I performed 100 searches using random industrial keywords, and I found no featured snippet in use - not from Grainger, MSC, or any of the other nationally known industrial distributor. This could be your chance to get ahead of them.</p>

<p>Get your featured snippet ranked high enough, and when someone asks for an orange Vitraulic coupling, your product could be the one read back by Siri.</p>


<p><b>2. Analyze Your Keyword Intent and Voice </b></p>

<p>A great deal of effort in Search Engine Optimization (SEO) is about developing the keywords and phrases that will best rank your site and pages in the search engine algorithm.  Typically, these are noun focused with maybe a few adjectives sprinkled in (mostly on the consumer side) for computers to best match the order and the weight of the words.</p>

<p>That's not how voice search works. Voice search is more focused on the patterns that we speak.  For example, I could type in a search form "buy Victraulic 107N Coupling", but I may voice search for "find the closest victraulic distributor with a 107N coupling".  The intent is different between the two searches.  You have to include conversational keywords in your keyword development and bid strategies to capture keywords like the way we speak and not necessarily the pattern we type.</p>

<p>Homework: review the list of keywords you have focused on your website and are bidding on in paid advertising.  Could you enhance that keyword list with more conversations phrases or reorder the words in the keyword phrases to better capture how we talk?  Hint: speak the search out loud, and see if it makes sense. </p>

<p>With more and more people using Voice Search, we need to change our marketing methods to include the way we speak.</p>


<p><b>3. Have you Claimed your Google My Business account? </b></p>

<p>There is a simple trick you can add to your Google searches in the browser that will find products or services near your current location -- just add "near me" to the search box.  When Google detects the search is coming from a mobile device, it already adds the location-centric search as the default.</p>

<p>You need to register your locations, including all of your branches, so they appear in local searches.</p>

![Badge](/images/googlemybusiness.png){: .center-image}

<p>Homework: claim your Google Local, Google My Business, and Bing Places for Business.  It's no cost and a no brainer.</p>

<p>Being listed locally will aid in surfacing your website and products to voice searchers.</p>


<p><b>4. Have you reviewed your page speed? </b></p>

<p>The common metric for page speed is 3 seconds from when a user first comes to your website to view a page to the time it is rendered.  Take any longer, and the user will press the back button.  With voice search, patience for slow loading pages is going to be even shorter.  It is important to analyze your page speed to ensure you are providing the fastest service possible to your users.</p>

<p>Use the free tool PageSpeed Insights provided by Google which will analyze every page from a desktop browser and mobile view point looking for opportunities to speed up the page loading time.  Pay particular attention to Mobile devices; that is the source of most voice searches.</p>

![Badge](/images/pagespeed-insights.jpg){: .center-image}

<p>Bonus: increased page speed will also improve your page rank in search engines.</p>

<p>Homework: load your main page, a random category page, and a random product page in PageSpeed Insight.  Chances are your page frame work will render other examples of each just the same.  Take note of the recommendations and place them on your product roadmap for implementation sooner rather than later.</p>

<p>People use voice search to get a quick answer. If your page loads slower than others, it will adversely affect your rank and effectiveness to reach the people searching for your product.</p>

<p><small>
Tags: 	
  {% for tag in page.tags %}
    <a href="/tags/{{ tag }}/">{{ tag }}</a>
  {% endfor %}
</small></p>