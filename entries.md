---
layout: page
title: Entries
---

{% for post in site.posts %}
  * {{ post.date | date_to_string }} <small>({{ post.category }})</small> &raquo; [ {{ post.title }} ]({{ post.url }})
{% endfor %}
