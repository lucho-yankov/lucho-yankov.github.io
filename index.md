---
layout: page
title: ""
description: ""
---
{% include JB/setup %}

{% for post in site.posts limit 5 %}
<article>
  <header>
    <h1><a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></h1>
    <p>(<time datetime="{{ post.date | date: "%Y-%m-%d" }}">{{ post.date | date_to_string }}</time>)</p>
  </header>
  <p class="entry-content">
    {% if post.content contains "<!-- read more -->" %}
        {{ post.content | split:"<!-- read more -->" | first | strip_html | truncatewords:50 }}
    {% else %}
        {{ post.content | strip_html | truncatewords:50 }}
    {% endif %}
    <br/>
    <a href="{{ post.url }}">Read more</a>
  </p>
</article>
{% endfor %}

