---
layout: page
title: Tutorials
permalink: /tutorials/
---

<ul class="tutorial-list">
{% for tutorial in site.tutorials %}
  <li>
    <h2><a href="{{ tutorial.url | prepend: site.baseurl }}">{{ tutorial.title }}</a></h2>
  </li>
{% endfor %}
</ul>
