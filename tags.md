---
layout: default
title: 小说目录
permalink: /tags/
---

<br>

<div id='tag_cloud'>
{% for tag in site.tags %}
<a href="#{{ tag[0] }}" title="{{ tag[0] }}" rel="{{ tag[1].size }}">{{ tag[0] }} ({{ tag[1].size }})</a> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
{% endfor %}
</div>


{% for tag in site.tags %}
<ul class="listing">
  <h2  id="{{ tag[0] }}">{{ tag[0] }} </h2>
{% for post in tag[1] %}
  <li class="listing-item">
  <time datetime="{{ post.date | date:"%Y-%m-%d" }}">{{ post.date | date:"%Y-%m-%d" }}</time>
  <a href="{{ site.url }}{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a>
  </li>
{% endfor %}
</ul>
{% endfor %}


<script src="/js/jquery.tagcloud.js" type="text/javascript" charset="utf-8"></script>
<script language="javascript">
$.fn.tagcloud.defaults = {
    size: {start: 1, end: 2, unit: 'em'},
      color: {start: '#ada8b5', end: '#000000'}
};

$(function () {
    $('#tag_cloud a').tagcloud();
});
</script>
