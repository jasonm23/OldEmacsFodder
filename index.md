---
layout: page
title: Emacs Fodder
tagline: all new, all Emacs...
---
{% include JB/setup %}

I have some old Emacs bits at
[http://jasonm23.github.com](http://jasonm23.github.com)  (before I
started using Jekyll, to do these pages..)

Meanwhile...

<div class="boxlist">
  {% for post in site.posts %}
      <div class="box">
          <h2> <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a> </h2>
          <p> {{ post.description }} </p>
          <p> <em><strong>posted:</strong> <span>{{ post.date | date_to_string }}</span></em> </p>
      </div>
  {% endfor %}
</div>


