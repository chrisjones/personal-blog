---
layout: post
cover: whiskey-glencairn.jpg
categories: posts
tags: startups
---

We recently changed our pricing model for PlanITDR from flat rate/month to a per device per month strategy. Of course we needed to model the pricing structure taking into account customers with larger fleets of backup devices.

This was our initial stab at pricing:

<table>
	<tr>	<td>1-25 devices</td>	<td>&nbsp;&nbsp;$10</td>	</tr>
	<tr>	<td>26-50 devices</td>	<td>&nbsp;&nbsp;$7.50</td>	</tr>
	<tr>	<td>51-150 devices</td>	<td>&nbsp;&nbsp;$5</td>		</tr>
	<tr>	<td>151+ devices</td>	<td>&nbsp;&nbsp;$2.50</td>	</tr>
</table>

<br />
Turns out the boundaries really hurt:

<table>
	<tr>	<td>25 devices</td>		<td>$250</td>	<td>&nbsp;</td>	</tr>
	<tr>	<td>26 devices</td>		<td>$195</td>	<td>&nbsp;&nbsp;drop $55 in revenue</td>	</tr>
	<tr>	<td>33 devices</td>		<td>$247.50</td>	<td>&nbsp;</td>	</tr>
	<tr>	<td>34 devices</td>		<td>$255</td>	<td>&nbsp;&nbsp;move up a tier, have to add 9 devices to increase revenue</td>	</tr>
</table>
<br />
<table>
	<tr>	<td>34 devices</td>		<td>$255</td>	<td>&nbsp;</td>		</tr>
	<tr>	<td>50 devices</td>		<td>$375</td>	<td>&nbsp;</td>		</tr>
	<tr>	<td>51 devices</td>		<td>$255</td>	<td>&nbsp;&nbsp;drop $80 in revenue</td>	</tr>
	<tr>	<td>75 devices</td>		<td>$375</td>	<td>&nbsp;&nbsp;move up a tier, have to add 25 devices to increase revenue</td>	</tr>
</table>

<br />
Well that isn't going to work, so I did some pricing models research and this graph shows what I didn’t understand before modeling above:


![Volume vs. Tiered Pricing](/images/tiered_pricing.png){:width="75%"}


I assumed volume pricing, i.e. take the number of backup appliances the MSP manages, then multiply that number times the price of their band, i.e. 41 devices is 41 * $7.50 = $307.50

But the correct answer is “graduated” tiered pricing, i.e. 41 devices is 25 * $10 + (41 - 25) * $7.50 = $370.

Playing with the rate and tiers, I can get to our current average revenue:

<table>
	<tr>	<td>&nbsp;</td>	<td>&nbsp;&nbsp;rate</td>	<td>&nbsp;&nbsp;discount</td>	</tr>
	<tr>	<td>1-25 devices</td>	<td>&nbsp;&nbsp;$5.00</td>	<td>&nbsp;</td>	</tr>
	<tr>	<td>26-50 devices</td>	<td>&nbsp;&nbsp;$4.50</td>	<td>&nbsp;&nbsp;10%</td>	</tr>
	<tr>	<td>51-150 devices</td>	<td>&nbsp;&nbsp;$3.75</td>	<td>&nbsp;&nbsp;25%</td>	</tr>
	<tr>	<td>151+ devices</td>	<td>&nbsp;&nbsp;$3.00</td>	<td>&nbsp;&nbsp;40%</td>	</tr>
</table>

<br />
The new pricing scheme comes within $100 total revenue of the flat rate pricing model - so essentially the average monthly invoice across our current MSP customer-base does not change. A MSP with exactly 150 devices will pay $562.50.

Another is this model:

<table>
	<tr>	<td>&nbsp;</td>	<td>&nbsp;&nbsp;rate</td>	<td>&nbsp;&nbsp;discount</td>	</tr>
	<tr>	<td>1-25 devices</td>	<td>&nbsp;&nbsp;$10.00</td>	<td>&nbsp;</td>	</tr>
	<tr>	<td>26-50 devices</td>	<td>&nbsp;&nbsp;$5.00</td>	<td>&nbsp;&nbsp;50%</td>	</tr>
	<tr>	<td>51-150 devices</td>	<td>&nbsp;&nbsp;$2.50</td>	<td>&nbsp;&nbsp;75%</td>	</tr>
	<tr>	<td>151+ devices</td>	<td>&nbsp;&nbsp;$1.00</td>	<td>&nbsp;&nbsp;90%</td>	</tr>
</table>

<br />
New pricing scheme yields a $5,300 increase per month for our current MSP customer base. A MSP with exactly 150 devices will pay $625.

Lots to price experiment!

<p><small>
Tags: 	
  {% for tag in page.tags %}
    <a href="/tags/{{ tag }}/">{{ tag }}</a>
  {% endfor %}
</small></p>