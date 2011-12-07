---
layout: post
title: "Setting up the blog using Octopress"
date: 2011-12-07 13:49
comments: true
categories: 
published: true
---

![Zack's Quest](https://img.skitch.com/20111207-p8sni6h2eyyac4dg65wpmpahx8.jpg)

I've been wanting to migrate the blog from Wordpress over to a Jekyll/Octopress blogging framework for tech geeks but haven't really had the time with my crazy schedules.

And then I realized it doesn't actually take too much time to set Octopress up and deploy, especially if you are deploying to Github pages or Heroku.

If you're looking to migrate from Wordpress as well, here's an outline of the steps I took:

#### 1. Make sure you have Ruby 1.9.2+ and Clone Octopress ####
```
git clone git://github.com/imathis/octopress.git octopress
cd octopress
```

#### 2. Install dependencies and install the default Ocotpress theme ############
bundle install
rake install
```

#### 3. Export and convert WordPress blog posts you want to migrate ####

Export WordPress blog entries you want to migrate and use [exitwp](https://github.com/thomasf/exitwp) to convert them to markdown.  Put the converted entries into your `source/_posts` folder.

#### 4. Set up a Github page ####

If you want a Github page with subdomain called username/organization, set up a Github repository like `username.github.com` or `organization.github.com`
Next, run Octopress's Github Pages setup:

```
rake setup_github_pages
```

It will ask you for your Github repository URL so throw in the SSH URL for your Github repository.

#### 5. Generate the blog and deploy ####

```
rake generate
rake deploy
```

#### 6. Commit the source of your blog ####

```
git add .
git commit -m 'your message'
git push origin source
```

#### 7. View your blog on local ####

```
rake preview
```

#### 8. Set up your custom domain ####

I'll leave this to you with Octopress's own instructions at [Custom Domains](http://octopress.org/docs/deploying/github#custom_domains).


Enjoy!