---
layout: post
title: Site Updates (Feb 2021)
date: '2021-02-18 23:30:00'
categories: [blog]
---

Over the past week, I’ve made a handful of changes to the site. It’s been a long time since I’ve made any appreciable updates to the site. I’ve moved to a new host, implemented dark mode and added category support. I consider them quality of life updates. None of these changes are groundbreaking, but these are things I’ve wanted to do on the site for a while now.

Previously, I was using [GitHub Pages](https://pages.github.com/) to host the site. But I wanted a bit more control over things. This week, I moved to [Netlify](https://www.netlify.com/). Netlify has the same ease of use that GitHub Pages provides, but I get a bit more insight into what’s happening during site deployments.

<div class="py-3">
	<div class="card shadow-sm">
		<img class="img-fluid" src="/public/images/2021/site-updates-feb-2021/site-dark-mode.png">
		<div class="card-body mx-auto">
			<small>Dark Mode Support</small>
		</div>
	</div>
</div>

I’ve also implemented dark mode support on the site. I’ve been using a [Jekyll](https://jekyllrb.com/) theme called [Lanyon](https://lanyon.getpoole.com/) for a few years now. The theme has been great, but it doesn’t support dark mode out of the box. Adding it wasn’t too bad, but I’ve probably done it in the most inefficient way possible and missed a handful of elements.

<div class="py-3">
	<div class="card shadow-sm">
		<img class="img-fluid" src="/public/images/2021/site-updates-feb-2021/categories.png">
		<div class="card-body mx-auto">
			<small>Category support!</small>
		</div>
	</div>
</div>

The lack of categories is something that’s been bugging me for a long time. I’ve finally added support for them. Well, kind of. Jekyll (the software that runs this site) already supports categories, but the Lanyon theme doesn’t (out of the box). Adding support for categories was easy enough. Each post will show the categories for that post (see the image above). I’ve also created a [categories page](/categories). So you can browse posts by categories.

I’ve been thinking about a complete redesign for the site. I’m not sure if I want a new Jekyll theme, or if I want to roll my own design for the site. A new Jekyll theme would be an easy way to get a new look. The themes I’ve seen out there aren’t quite what I want. I’m not sure I have the time (or energy) to roll my own new theme/look for the site.

Please enjoy the new features of the site.

