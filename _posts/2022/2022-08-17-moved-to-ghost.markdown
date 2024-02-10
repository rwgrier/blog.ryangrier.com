---
layout: post
title: Moved From Jekyll to Ghost
date: '2022-08-17 00:59:32'
categories: [blog]
---

I've recently made changes to this site. It was a lot of changes. This post goes through the changes I've made. These changes include the software running the site, where the site is hosted, and the domains I'm using.

## Blogging Software

The blogging software I previously used was [Jekyll](https://jekyllrb.com). It was nice because I would write the blog posts in [Markdown](https://daringfireball.net/projects/markdown/).

I like this because it was free and Jekyll allowed my blog posts to be portable. But this portability added friction to my posting process. This has all been working fine. But I've wanted to streamline how I get posts onto the site.

Currently, I will write the post in [iA Writer](https://ia.net/writer), export the Markdown to a text editor (like [Nova](https://nova.app) or [BBEdit](https://www.barebones.com/products/bbedit/index.html)), commit the changes to Github, push them up and wait. It's a bit of a [Rube Goldberg Machine](https://en.wikipedia.org/wiki/Rube_Goldberg_machine).

I almost always make a typo or two during this process and need to push up additional changes.

This process got more complicated on the iPad. I'm not sure if it's the text editor I'm using there, but I always end up with formatting issues with the post [front matter](https://jekyllrb.com/docs/front-matter/).

I started looking into blogging software that would allow me to streamline things. I like using iA Writer and want to continue to use it. I've used [Ulysses](https://ulysses.app) in the past to write blog posts and could always move back to it.

iA Writer will publish directly to a few blogging services. Those blogging services include [Ghost](https://ghost.org), [Medium](https://medium.com), [Micro.blog](https://micro.blog), [Micropub](https://en.wikipedia.org/wiki/Micropub_(protocol)), and [Wordpress](https://wordpress.org). Ulysses also supports Ghost, Medium, [Micro.blog](https://Micro.blog), and WordPress.

I looked into [Micro.blog](https://Micro.blog), WordPress, Medium, and Ghost.

I wanted to use [Micro.blog](https://Micro.blog). I like supporting (more) indie developers. I tried to use it, but I did. I imported all my old posts (once I made modifications), but I wasn't happy with the themes and didn't want to modify/create my own.

WordPress is good, but I've used it before. I tried setting up a site and had trouble importing the posts. I wasn't interested in doing everything by hand. I gave up.

I looked into Medium for about a minute. I want to use my blog site with a custom domain and Medium doesn't currently support custom domains. Medium keeps flipping back on forth on whether they support custom domains. Medium also drives me nuts with the paywalls. Medium looks great and has a great editor. However, the lack of custom domain support is a non-starter for me.

Ghost was interesting to me. I've never used it before and wanted to look into it. The Jekyll migration/import process was non-existent. I did find an [old script online](https://github.com/mekomlusa/Jekyll-to-Ghost) that created a JSON file to import, but it only included the titles and dates (which was helpful). I then had to go through and paste the post content. It was a pain, but it gave me a chance to update my links. I also got to read through all the old posts again. The editor is the most like Medium's available, it may be slightly better.

I ended up going with Ghost as the blogging software for the site. The editor is great. I like the themes. Best of all, I can publish (a draft) directly from either iA Writer or Ulysses.

## Hosting

I've been hosting the site and blog using either [Netlify](https://www.netlify.com) or [Github Pages](https://pages.github.com/) for years.

About a year and a half ago, I [moved the site]({%post_url /2021/2021-02-18-site-updates-feb-2021 %}) from Github Pages to Netlify. I forget why I moved. There may have been a Jekyll plugin that I wanted to use that Github Pages didn't support, but I could be wrong.

Once I decided on using Ghost, I had to decide where to host the site. I looked at a few options. [Ghost Pro](https://ghost.org/pricing/), Do it yourself (DYI) using [DigitalOcean](https://marketplace.digitalocean.com/apps/ghost) and [DigitalPress](https://www.digitalpress.blog).

Ghost Pro is probably the best option, but it's pricey. If I want to use the theme I'm currently using ([Attila](https://github.com/zutrinken/attila)) I would have to go with the Creator plan. I like my site, but I don't want to pay $25/month for it. That's steep.

DigitalOcean is a nice way to host sites. It looks easy enough to set up and configure a Ghost site. They have a 1-click install. I'm not sure I want to maintain the server and install updates.

DigitalPress is a service that kept popping up when I was looking for Ghost hosting. They aren't US-based, but I can live with that. The pricing is much more reasonable. For about $7/month (after the EUR to USD conversion), I get hosting and automatic updates. DigitalOcean was $6/month and I needed to handle the updates myself. DigitalPress even has free hosting options.

I'm currently going with DigitalPress. It was easy to set up and get running. I've been using it for about a week, but I have been impressed.

## Domain Name

As a part of all this, I've switched domains from [ryan.grier.co](https://ryan.grier.co) back to [www.ryangrier.com](https://www.ryangrier.com).

I started the site/blog out on [www.ryangrier.com](https://www.ryangrier.com) in 2001. That's over 20 years ago. It feels nice to get back to using that domain name. I thought [ryan.grier.co](https://ryan.grier.co) was clever, but I had to explain to people that it was .co and not .com.

I am now handling the [DNS](https://en.wikipedia.org/wiki/Domain_Name_System) entries through [CloudFlair](https://www.cloudflare.com) (again). They have a lot of nice features and helped me get the domains all pointing back in the right directions.

## In Conclusion

Getting these changes in place was a lot of work. I'm hoping it was all worth it. I think that it will streamline the posting process and allow me to write more posts.

I have a feeling that in a few years I'll change everything again. Knowing me, I'll make a change in a few weeks. 🤣

