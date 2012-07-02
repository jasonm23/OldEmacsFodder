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

<script type='text/javascript'>
  //<![CDATA[
    $(function(){
      $('#blocks').masonry({
        // options
        itemSelector : '.block',
      });
    });
  //]]>
</script>
<style>
  .block {
    background-color: #000;
    border: 2px solid #2d2d2d;
    border-radius: 10px;
    padding: 8px;
    margin: 8px;
    -moz-box-shadow: 0px 8px 15px #111;
    -webkit-box-shadow: 0px 8px 15px #111;
    box-shadow: 0px 8px 15px #111;
  }
  #blocks {
    
  }
</style>
<div id="blocks">
  {% for post in site.posts %}
      <div class="block span3" >
          <h2> <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a> </h2>
          <p> {{ post.description }} </p>
          <p> <em><strong>posted:</strong> <span>{{ post.date | date_to_string }}</span></em> </p>
      </div>
  {% endfor %}
</div>
<div style="clear:both; margin: 50px 0;">
</div>


