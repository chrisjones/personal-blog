---
layout: post
cover: whiskey-glencairn.jpg
categories: posts
tags: devops
---

Let's face it, if you've used Heroku, you love their easy deploy process - I know I do! But if you try to host a hobby project that requires access to the local filesystem, or in my case I want the site to be hosted on the naked domain without having to use DNSimple or another provider that has ALIAS records, then Heroku quickly becomes a problem.

### So I've created this easy breazy process to git deploy your website 

1. On the server, create a new repository in /var/git/ as the "code vault":

   ``` git init --bare /var/git/chrisjones.git```

2. Create a new post-deploy hook file named post-update

   ``` cd /var/git/chrisjones.git/hooks``` <br />
   ``` cp post-update.sample post-update```

3. Fill the file with this code for my Jekyll blog: 

   ```
   #!/bin/sh
   echo
   echo "**** Pulling changes into Live [Production's post-update hook]"
   echo
   cd /srv/chrisjones.dev || exit
   unset GIT_DIR
   git pull production master

   echo 
   echo "bundle install"
   echo
   ~/.rbenv/shims/bundle install

   echo 
   echo "Compiling assets..."
   echo
   JEKYLL_ENV=production ~/.rbenv/shims/bundle exec jekyll build

   exec git-update-server-info
   ```

4. Now create the web directory

   ``` mkdir /srv/chrisjones.dev```
   
5. Setup directory to receive code:

   ``` git init``` <br />
   ``` git remote add production /var/git/chrisjones.git```
   
6. Now on the local development machine add the repository to your git config:

   ``` git remote add production webserver:/var/git/chrisjones.git```

7. Now simply deploy!

   ``` git push production master```
   

### Whenever you have an update, or I want to create a new post, I simply commit the code and deploy to production. Boom!


<p><small>
Tags: 	
  {% for tag in page.tags %}
    <a href="/tags/{{ tag }}/">{{ tag }}</a>
  {% endfor %}
</small></p>