---
layout: archive
permalink: /
title: "Posts"
author_profile: true
redirect_from:
  - /blog
  - /posts
  - /year-archive
---

{% include base_path %}
{% capture written_year %}'None'{% endcapture %}
{% for post in site.posts %}
  {% capture year %}{{ post.date | date: '%Y' }}{% endcapture %}
  {% include archive-single.html %}
{% endfor %}
