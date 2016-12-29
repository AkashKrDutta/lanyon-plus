---
layout: default
permalink: index.html
title: AKD
description: "Blogging on github.io"
---
{% comment %}
## [lanyon-plus](https://github.com/dyndna/lanyon-plus)

Based on Jekyll theme: [Lanyon](http://lanyon.getpoole.com) by [**Mark Otto**](https://github.com/mdo)

* add-ons by [Samir Amin](http://sbamin.com)
* [Site features]({{ site.url}}/disclosure#i-classfa-fa-thumbs-o-up-credits-for-site-featuresi)
* License: Open sourced under the [MIT license](http://sbamin.com/disclosure/#theme-major-credit--license). 

Maximum four posts on front page where first two posts are featured, and remaining are date sorted.
{% endcomment %}
## **Welcome**
<p style="text-align:right"><span style="font-style:italic">Quote</span><br>"By experiencing both, victory and defeat, running away and<br>	 shedding tears, a man will become a man."<br> <span style="font-style:italic">&mdash;&nbsp;Shanks, One Piece</span> </p>
Thanks for visiting my homepage and considering your time worthy for my introduction! Hi! myself an enthusiastic sophomore from Computer Science and Engineering Department, IIT KANPUR. In Computer Science, my areas of interest are <code>parallel programming</code>, <code>web development</code>, <code>competitive programming</code> and <code>gamedev</code>.<br> Hope you get some useful stuff around here!<br>
{% comment %}
{% if site.twitter_widget_id %}
<div class="text-tweets">
<div class="tweets">
<a class="twitter-timeline"
  data-dnt="true"
  width="600"
  height="250"
  href="https://twitter.com/{{ site.owner.twitter }}"
  data-widget-id="{{ site.twitter_widget_id }}"
  data-tweet-limit="2"
  data-chrome="noheader nofooter noborders noscrollbar transparent">
  Recent Tweets</a>
</div>
<script>
    !function(d,s,id){var js,fjs=d.getElementsByTagName(s)[0],p=/^http:/.test(d.location)?'http':'https';if(!d.getElementById(id)){js=d.createElement(s);js.id=id;js.src=p+"://platform.twitter.com/widgets.js";fjs.parentNode.insertBefore(js,fjs);}}(document,"script","twitter-wjs");
</script>
</div>
{% else %}
Twitter stream will show up here if `twitter_widget_id` is present is `_config.yml`. [Demo](http://sbamin.com)
{% endif %}
{% endcomment %}

<div class="posts">
  {% for post in site.categories.featured limit:2 %}
  <div class="post">
    <h1 class="post-title">
      <a href="{{ site.url }}{{ post.url }}">
        {{ post.title }}
      </a>
    </h1>

  {% if post.modified.size > 2 %}<span class="post-date indexpg" itemprop="dateModified" content="{{ post.modified | date: "%Y-%m-%d" }}"><i class="fa fa-edit" title="Last updated"> {{ post.modified | date_to_string }}</i> <a href="{{ site.url }}/featured" title="Featured posts"><i class="fa fa-paperclip" title="Featured" class="social-icons"></i></a></span>{% else %}<span style="display:inline" class="post-date indexpg" itemprop="datePublished" content="{{ post.date | date: "%Y-%m-%d" }}"><i class="fa fa-calendar" title="Date published"> {{ post.date | date_to_string }}</i> <a href="{{ site.url }}/featured#disqus_thread" title="Featured posts"><i class="fa fa-paperclip" title="Featured" class="social-icons"></i></a></span>
,&nbsp;<a href="{{ site.url }}{{ post.url }}#disqus_thread" style="display:inline">link</a>
{% endif %}
<br>
 {% if post.description.size > 140 %}{{ post.description | markdownify | remove: '<p>' | remove: '</p>' }}{% else %}{{ post.excerpt | markdownify | remove: '<p>' | remove: '</p>' }}{% endif %} <a href="{{ site.url }}{{ post.url }}" title="Read more"><strong>Read more...</strong></a>
  </div>
  <hr class="transp">
  {% endfor %}
</div>

<div class="posts">
  {% for post in site.posts limit:2 %}
  {% unless post.category contains "featured" %}
  <div class="post">
    <h1 class="post-title">
      <a href="{{ site.url }}{{ post.url }}">
        {{ post.title }}
      </a>
    </h1>

  {% if post.modified.size > 2 %}<span class="post-date indexpg" itemprop="dateModified" content="{{ post.modified | date: "%Y-%m-%d" }}"><i class="fa fa-edit" title="Last updated"> {{ post.modified | date_to_string }}</i></span>{% else %}<span style="display:inline-block" class="post-date indexpg" itemprop="datePublished" content="{{ post.date | date: "%Y-%m-%d" }}"><i class="fa fa-calendar" title="Date published"> {{ post.date | date_to_string }}</i></span>
,&nbsp;<a href="{{ site.url }}{{ post.url }}#discus_thread">link</a>
{% endif %}
<br>
 {% if post.description.size > 140 %}{{ post.description | markdownify | remove: '<p>' | remove: '</p>' }}{% else %}{{ post.excerpt | markdownify | remove: '<p>' | remove: '</p>' }}{% endif %} <a href="{{ site.url }}{{ post.url }}" title="Read more"><strong>Read more...</strong></a>
  </div>
  {% unless forloop.last %}<hr class="transp">{% endunless %}
  {% endunless %}
  {% endfor %}
</div>
<h3 class="post-title">
<div class="pagination" style="margin: 0.5rem;">
    <a class="pagination-item older" href="{{ site.url }}/blog"><i class="fa fa-edit"> Blog</i></a>
    <a class="pagination-item newer" href="{{ site.url }}/tags"><i class="fa fa-tags"> Tags</i></a>
</div>
</h3>
