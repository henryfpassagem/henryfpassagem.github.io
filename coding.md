---
layout: post-index
permalink: /coding/
title: Coding
tagline: Coding topics
tags: [coding]
comments: false
---

{% assign grouped_posts = site.coding | group_by_exp: "post", "post.categories | first" %}

{% for category in grouped_posts %}
  {% assign category_name = category.name %}
  <h2>{{ category_name }}</h2>

  {% assign subcategories = category.items | group_by: "subcategory" %}

  <ul>
    {% for subcategory in subcategories %}
      <li><strong>{{ subcategory.name }}</strong>
        <ol>
          {% for post in subcategory.items %}
            <li><a href="{{ post.url }}">{{ post.title }}</a></li>
          {% endfor %}
        </ol>
      </li>
    {% endfor %}
  </ul>
{% endfor %}
