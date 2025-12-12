---
layout: page
title: News
permalink: /news/
nav: true
nav_rank: 4
---
{% for n in site.news | sort: "date" | reverse %}
<h3><a href="{{ n.url | relative_url }}">{{ n.title }}</a></h3>
<p>{{ n.summary | default: n.excerpt }}</p>
<a href="{{ n.url | relative_url }}">Read more →</a>
<hr>
{% endfor %}