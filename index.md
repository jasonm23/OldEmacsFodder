---
layout: page
title: Emacs Fodder
tagline: slanted to OS X and Emacs 24.
---
{% include JB/setup %}

Notes on my efforts to customize and beautify Emacs.

<ul class="posts">
  {% for post in site.posts %}
    <h2> <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a> </h2>
    <p> {{ post.description }} </p>
    <p> <em><strong>posted:</strong> <span>{{ post.date | date_to_string }}</span></em> </p>
  {% endfor %}
</ul>


