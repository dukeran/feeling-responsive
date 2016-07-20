---
layout: blog
show_meta: true
title: "Code for Thought"
subheadline: "Layouts of Feeling Responsive"
header:
   image_fullwidth: "header_unsplash_5.jpg"
permalink: "/code/"
---
<ul>
    {% for post in site.categories.code %}
    <li><a href="{{ site.url }}{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
</ul>

{% for post in site.categories.code %} {% include _pagination_small.html %} {% endfor %}