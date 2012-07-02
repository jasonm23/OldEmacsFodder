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



.block * { 
    color: #514A41; 
    text-shadow: none;
}



/*
#CCBBA3 #CCBBA3 #CCBBA3 : 100% 
#B7A892 #CCBCA7 #CCB8A3 : 90% 
#A39582 #CCBEAB #CCB6A3 : 80% 
#8E8272 #CCC0AF #CCB3A3 : 70% 
#7A7061 #CCC1B3 #CCB1A3 : 60% 
#665D51 #CCC3B7 #CCAEA3 : 50% 
#514A41 #CCC5BB #CCACA3 : 40% 
#3D3830 #CCC6BF #CCAAA3 : 30% 
#282520 #CCC8C3 #CCA7A3 : 20% 
#141210 #CCCAC7 #CCA5A3 : 10% 
#000000 #CCCCCC #CCA3A3 : 0% 


#CCBBA3 #CCBBA3 #CCBBA3 : 100% 
#B7A892 #CCBCA7 #CCB8A3 : 90% 
#A39582 #CCBEAB #CCB6A3 : 80% 
#8E8272 #CCC0AF #CCB3A3 : 70% 
#7A7061 #CCC1B3 #CCB1A3 : 60% 
#665D51 #CCC3B7 #CCAEA3 : 50% 
#514A41 #CCC5BB #CCACA3 : 40% 
#3D3830 #CCC6BF #CCAAA3 : 30% 
#282520 #CCC8C3 #CCA7A3 : 20% 
#141210 #CCCAC7 #CCA5A3 : 10% 
#000000 #CCCCCC #CCA3A3 : 0% 

*/

.block {
    background-color: #CCC8C3;
    border: 2px solid #CCC1B3;
    border-radius: 10px;
    margin: 8px;
    padding: 12px;
    -moz-box-shadow: 0px 12px 25px #000;
    -webkit-box-shadow: 0px 12px 25px #000;
    box-shadow: 0px 12px 25px #000;
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


