---
layout: post
cover: whiskey-glencairn.jpg
categories: posts
tags: analytics
---

<i>Originally posted March 8 on academy.b2xpartners.com</i>

Let's have a short talk on site search.

You've enabled the feature in Google Analytics > Admin > View > View Settings and entered in the query parameter (like q or keyWord for example). Now you have a nice list of what your visitors are searching for on your website including how many unique times that term was searched, how many pages the visitor scrolled before they found their result, and whether they refined the search or not. 

But where did they go? What product did they click on? Just add a secondary dimension: Search Destination Page to the Behavior > Site Search > Search Terms report:

![Sample KPI](/images/search_dimension.png)

Then you can see where your visitors went:

![Sample KPI](/images/search_terms.png)

What can you learn from this report?

1. Seven website exits, should the terms match a product in your catalog? If so, you need to implement a synonym.

2. Look at your refinements, this screenshot tells a better story than above:

	![Sample KPI](/images/synonyms.png)

	There's three refinements on the same search, obviously the visitor is not finding what they are looking for. This could be because your indexes are too small, or you aren't boosting the right elements. For example, in this search, the results page did not have the Manufacturer Grove Gear listed at the top of the results.

3. For the searches that produced product detail pageviews, #2 & #7, are those the most appropriate products for that term? Should you boost another product or manufacturer to the first page for that term?

 

Recommendation:

The results above are for a very short period of time - a few days. I recommend reviewing these results every 30-60 days so the numbers are more comprehensive. Ignore the bottom 25%, you can worry about the long-tail after the heavily searched terms are optimized.

Put a recurring appointment on your calendar to review what your visitors are searching for; decipher their intent with a product manager; and update indexes, add synonyms, and/or boost products and/or manufacturers to put the right products on the first results screen.

Make it easier for your customers to buy from you!


<p><small>
Tags: 	
  {% for tag in page.tags %}
    <a href="/tags/{{ tag }}/">{{ tag }}</a>
  {% endfor %}
</small></p>