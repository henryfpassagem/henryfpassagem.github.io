---
layout: post-index
permalink: /articles/
title: articles
tagline: Coding topics
tags: [articles]
comments: false
---

{% assign grouped_posts = site.articles | group_by: "subcategory" %}

{% for category in grouped_posts %}
  <h2>{{ category.name }}</h2> <!-- Exibe "docker", "using-container", etc. -->

  <ul>
    {% for post in category.items %}
      <li><a href="{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
  </ul>
{% endfor %}




<!-- {% for post in site.categories.coding %}
  {% capture category1 %}{{ post.categories[0] }}{% endcapture %}
  {% capture category2 %}{{ post.categories[1] }}{% endcapture %}
  
  <h2>{{ category1 }} > {{ category2 }}</h2>
  <h3><a href="{{ site.url }}{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a></h3>
  <p><i><small>Posted: {{ post.date | date: "%B %-d, %Y"}} Updated: {{ post.modified | date: "%B %-d, %Y"}}</small></i></p>
  <p>{{ post.excerpt | strip_html | truncate: 160 }}</p>
{% endfor %} -->