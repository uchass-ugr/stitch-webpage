---
layout: page
title: News
permalink: /news/
nav: true
nav_rank: 4
---
{% assign news = site.news | sort: "date" | reverse %}

{% for item in news %}
  <div class="news-item">
    <p><small>{{ item.date | date: "%b %Y" }}</small></p>

    <h3>
      <a href="{{ item.url | relative_url }}">{{ item.title }}</a>
    </h3>

    <p>
      {{ item.summary | default: item.excerpt | strip_html | truncate: 200 }}
    </p>

    <p>
      <a href="{{ item.url | relative_url }}">Leer más →</a>
    </p>

    <hr>
  </div>
{% endfor %}