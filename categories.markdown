---
layout: page
title: Categories
permalink: /categories/
---

{% for category in site.categories %}
  <div class="pb-5">
	{% capture category_name %}{{ category | first }}{% endcapture %}
	<div id="#{{ category_name | slugize }}"></div>
	
	<h3>{{ category_name }}</h3>
	<a name="{{ category_name | slugize }}"></a>
	{% for post in site.categories[category_name] %}
	<article class="archive-item">
	  <a href="{{ site.baseurl }}{{ post.url }}">{% if post.title and post.title != "" %}{{post.title}}{% else %}{{post.excerpt |strip_html}}{%endif%}</a>
	</article>
	{% endfor %}
  </div>
{% endfor %}
