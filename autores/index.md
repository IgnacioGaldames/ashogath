---
layout: page
title: Autores
description: Perfiles de quienes publican relatos y ensayos en la revista Ashogath.
permalink: /autores/
---

<ol class="reading-list">
  {% assign ordered_authors = site.authors | sort_natural: "name" %}
  {% for author in ordered_authors %}
  <li>
    <a href="{{ author.url | relative_url }}">
      <span class="list-mark" aria-hidden="true">{{ author.monogram | escape }}</span>
      <h2>{{ author.name | escape }}</h2>
      <span class="list-meta">{{ author.contribution | escape }}</span>
    </a>
  </li>
  {% endfor %}
</ol>
