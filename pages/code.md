---
layout: page
show_meta: true
title: "Code for Thought"
subheadline: "Layouts of Feeling Responsive"
header:
   image_fullwidth: "header_unsplash_5.jpg"
permalink: "/code/"
---

Welcome to the Code for thought Blog page! 


{% for post in site.categories.code %} {% include _pagination_small.html %} {% endfor %}