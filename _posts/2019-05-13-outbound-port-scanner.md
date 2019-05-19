---
layout: post
cover: whiskey-glencairn.jpg
categories: posts
tags: security
---

I was on an engagement today where all of my meterpreter payloads were being blocked - regardless if the payload was cretaed from setoolkit, DKMC, or msfvenom. This organization is very security-mature so it should have been no surpise. 

So I took a step back and asked myself, "What ports are open?" Here's a little powershell script to identify the open ports on the firewall:

```powershell
#Select port range
$portrange = 20..1000
#Open connection for each port from the range
Foreach ($p in $portrange)
{
$Socket = New-Object Net.Sockets.TcpClient      
$ErrorActionPreference = 'SilentlyContinue'
#Connect on the given port
$Socket.Connect("178.33.250.62", $p)
#Determine if the connection is established
if ($Socket.Connected) {
Write-Host "Outbound port $p is open." -ForegroundColor Green
$Socket.Close()
}
else {
Write-Host "Outbound port $p is closed or filtered."}
} #end foreach
```  
   
&nbsp;  
### I suppose I could have just ran a meterpreter shell over https, but now I know for sure!  


<p><small>
Tags: 
  {% for tag in page.tags %}
    <a href="/tags/{{ tag }}/">{{ tag }}</a>
  {% endfor %}
</small></p>