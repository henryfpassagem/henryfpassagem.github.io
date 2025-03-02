---
layout: post-index
permalink: /coding/
title: Coding
tagline: Coding topics
tags: [coding]
comments: false
---

{% assign grouped_posts = site.coding | group_by: "categories" %}

{% for category in grouped_posts %}
  <h2>{{ category.name }}</h2>

  {% assign subcategories = category.items | group_by: "subcategory" %}

  <ul>
    {% for subcategory in subcategories %}
      <li><strong>{{ subcategory.name }}</strong>
        <ul>
          {% for post in subcategory.items %}
            <li><a href="{{ post.url }}">{{ post.title }}</a></li>
          {% endfor %}
        </ul>
      </li>
    {% endfor %}
  </ul>
{% endfor %}
