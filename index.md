---
layout: page
title: Emacs Fodder
tagline: slanted to OS X and Emacs 24.
---
{% include JB/setup %}

Welcome to EmacsFodder, this is a place I'll post my various emacs
things.

As of now, you'll find a set of Emacs icons, themes and a theme editor
at [http://jasonm23.github.com](http://jasonm23.github.com) so
perhaps, you'd like to see those.

Meanwhile...

<ul class="posts">
  {% for post in site.posts %}
    <h2> <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a> </h2>
    <p> {{ post.description }} </p>
    <p> <em><strong>posted:</strong> <span>{{ post.date | date_to_string }}</span></em> </p>
  {% endfor %}
</ul>


