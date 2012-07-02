---
layout: page
title: Emacs Fodder
tagline: all new, all Emacs...
---
{% include JB/setup %}

I have some old stuff in at [http://jasonm23.github.com](http://jasonm23.github.com) 

Meanwhile...

<ul class="posts">
  {% for post in site.posts %}
    <h2> <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a> </h2>
    <p> {{ post.description }} </p>
    <p> <em><strong>posted:</strong> <span>{{ post.date | date_to_string }}</span></em> </p>
  {% endfor %}
</ul>


