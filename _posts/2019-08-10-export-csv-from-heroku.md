---
layout: post
cover: whiskey-glencairn.jpg
categories: posts
tags: development devops planitdr
---
<br />
<h3>Background</h3>

PlanITDR has a "newish" feature not widely circulated where the app will assign a company a unique @pdr-intg.com email address, and that company can forward their backup status emails to PlanITDR. Then PlanITDR will collect those logs in the database, parse them, and display any alerts, errors, or warnings in FleetView - our single pane of glass for backup status regardless of technology vendor.

When we bring on a new technology vendor, we ask the companies to go ahead and forward the logs to the pdr-intg.com email which is eventually collected in the unprocessed\_logs table in the database. Then we can extract them and write the parser for that technology.

<h3>Extracting the Emails</h3>

```bash
# heroku pg:psql -r production
# select count(*) from unprocessed_logs;

 count
--------
  2004	

# \copy (select * from unprocessed_logs) TO unprocessed_logs.csv CSV DELIMITER ',' CSV HEADER

# \q
```
<br />


<p><small>
Tags: 	
  {% for tag in page.tags %}
    <a href="/tags/{{ tag }}/">{{ tag }}</a>
  {% endfor %}
</small></p>