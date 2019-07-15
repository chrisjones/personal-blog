---
layout: post
cover: whiskey-glencairn.jpg
categories: posts
tags: analytics
---

Setting up segmentation is usually a fire and forget task, but this has tripped me up enough that writing it down will help me remember it in the future!

I am helping an eCommerce website out building their analytics and dashboard platforms. As part of that, we desperately need to measure Registered/known users vs Guest/unknown users to help make decisions on AB Testing. 

The ERP/website developers are populating the dataLayer for me. A website visitor that is not logged in has a contact_id of 9999999, and after login, the visitor's contact_id in the dataLayer is updated to their database row id of the user account. Don't forget to protect your customer's privacy!

After creating the custom dimensions, I setup the segments:

#####Guest Segment - Contains UserID 9999999

![Guest Segment Include](/images/include_9999999.png)
 
#####Registered Segment - Does not Contain UserID 9999999

![Registered Segment Include](/images/registered_segment.png)

Everything looks logically correct, but the transactions are attributed to both Segments:

![Transactions Dual Attribution](/images/bad_guest_transactions.png)

Hmmmmmmmm. I ran a couple of reports to verify the UserId was coming across correctly. The best report is Sales Performance and add a secondary dimension of UserID to see each sale and the UserID that placed the order. That report confirmed that all sales that morning were from Registered users.

Then I had a thought, instead of the Guest segement including the UserID 9999999, let's create a double negative! Let's reset the segment to Exclude UserIDs that are not 9999999. 

#####Guest Segment - Exclude and Does Not Contain UserID 9999999

![Guest Segment Exclude](/images/guest_segment.png)

And boom:

![Transactions Corrected](/images/good_guest_transactions.png)

So lesson of the day? Use double negatives. hahaha


<p><small>
Tags: 	
  {% for tag in page.tags %}
    <a href="/tags/{{ tag }}/">{{ tag }}</a>
  {% endfor %}
</small></p>