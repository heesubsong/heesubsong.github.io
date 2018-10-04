---
title:  Post
layout: default
order: 2
---

{% for post in site.posts %}

{% assign item = post %}

{% include postbox.html %}

{% endfor %}


