---
layout: page
title: conda-forge blog
---
{% include JB/setup %}

<ul class="posts">
  {% for post in site.posts %}
    {% if post.draft != true %}
    <li><a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a>: <i>{{ post.date | date_to_string }}</i> </li>
    {% endif %}
  {% endfor %}
</ul>
