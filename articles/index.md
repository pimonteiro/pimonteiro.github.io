---
layout: page
title: Articles
excerpt: "An archive of articles sorted by date."
search_omit: true
---

{% if site.categories.articles == null %}
  <h2 text-align:"center">Nothing yet!</h2>
{% else %}
  <ul class="post-list">
  {% for post in site.categories.articles %}
    <li><article><a href="{{ site.url }}{{ post.url }}">{{ post.title }} <span class="entry-date"><time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%B %d, %Y" }}</time></span>{% if post.excerpt %} <span class="excerpt">{{ post.excerpt | remove: '\[ ... \]' | remove: '\( ... \)' | markdownify | strip_html | strip_newlines | escape_once }}</span>{% endif %}</a></article></li>
  {% endfor %}
  </ul>
{% endif %}
