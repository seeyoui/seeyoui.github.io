---
layout: default
---

<div>
  <ul class="listing">
  {% assign title_name = 'love' %}
  {% for post in site.posts reversed %}
  {% if post.title == title_name %}
  <article class="content">
    <section class="title">
      <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
    </section>
    <section class="meta">
    <span class="time">
      <time datetime="{{ post.date | date:"%Y-%m-%d" }}">{{ post.date | date:"%Y-%m-%d" }}</time>
    </span>
    {% if post.tags %}
    <span class="tags">
      {% for tag in post.tags %}
      <a href="/tags.html#{{ tag }}" title="{{ tag }}"><i class="fa fa-tag"></i>&nbsp;&nbsp;{{ tag }}</a>
      {% endfor %}
    </span>
    {% endif %}
    </section>
    <section class="post">
    {{ post.content }}
    </section>
    </article>
    {% break %}
  {% endif %}
  {% endfor %}
  </ul>
  <div class="divider"></div>
  <ul class="listing main-listing">
    <li class="listing-seperator"><i class="fa fa-heart-o"></i>&nbsp;&nbsp;新鲜的回忆</i>
  {% capture year %}{{ site.time | date:"%Y"}}{% endcapture %}
  {% for post in site.posts offset:1 %}
    {% capture y %}{{ post.date | date:"%Y"}}{% endcapture %}
    {% if year != y %}
    {% break %}
    {% endif %}
    <li class="listing-item">
      <time datetime="{{ post.date | date:"%Y-%m-%d" }}">{{ post.date | date:"%Y-%m-%d" }}</time>
      <a href="{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a>
    </li>
  {% endfor %}
    <li class="listing-seperator"><a href="/archive.html"><i class="fa fa-heart"></i>&nbsp;&nbsp;尘封的往事</a></li>
  </ul>
</div>
