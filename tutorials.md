---
layout: page
title: Tutorials
permalink: /tutorials/
---

{% for tutorial in site.tutorials %}
  <li>
    <h2><a href="{{ tutorial.url | prepend: site.baseurl }}">{{ tutorial.title }}</a></h2>
  </li>
{% endfor %}
