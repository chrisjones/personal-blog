---
layout: post
cover: whiskey-glencairn.jpg
categories: posts
---

I love letsencrypt, but I don't deploy servers often enough to commit this to memory, but I do create a lot of public-facing websites!

## Quick steps to get up and running:

1. Install, you only have to do this once per host. In this case, I'm using nginx:

   ```sudo yum install certbot python2-certbot-nginx```
   
   but it'll work for Apache, too. Just substitute nginx for apache in the above command.


2. Add your certificate

   ```sudo certbot --nginx certonly -d chrisjones.dev```
  

3. Configure nginx to host your server in /etc/nginx/conf.d/chrisjones-dev.conf:

	```
	server {
	  if ($host = www.chrisjones.dev) {
	    return 301 https://chrisjones.dev$request_uri;
	  }

	  server_name chrisjones.dev;
	  root /srv/chrisjones.dev;

	  listen 443 ssl;
	  ssl_certificate /etc/letsencrypt/live/chrisjones.dev/fullchain.pem; 
	  ssl_certificate_key /etc/letsencrypt/live/chrisjones.dev/privkey.pem;
	  include /etc/letsencrypt/options-ssl-nginx.conf; # managed by Certbot
	  ssl_dhparam /etc/letsencrypt/ssl-dhparams.pem; # managed by Certbot
	}

	server {
	  if ($host = www.chrisjones.dev) {
	    return 301 https://chrisjones.dev$request_uri;
	  }

	  if ($host = chrisjones.dev) {
	    return 301 https://$host$request_uri;
	  } 

	  listen 80;
	  server_name chrisjones.dev;
	  return 404;
	}
	```


4. Start or Reload nginx

5. Lastly, setup auto-renewal. Again, you only have to do this once per server in cron:

   ```
   # crontab -e

   15 3 * * * /usr/bin/certbot renew --quiet
   ```

### That'll quickly get you up and running with renewable certs from LetsEncrypt!
