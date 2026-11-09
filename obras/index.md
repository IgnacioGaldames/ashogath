---
layout: page
title: Lecturas
description: Cuentos y ensayos de la revista Ashogath, cada uno en una página propia y enlazado con su autor.
permalink: /obras/
---

Explora cada pieza por título, autor y tema. En cada lectura encontrarás el perfil de quien la escribió y enlaces a otras obras.

<ol class="reading-list">
  {% assign ordered_works = site.works | sort_natural: "order" %}
  {% for work in ordered_works %}
  {% assign author = site.authors | where: "slug", work.author | first %}
  <li>
    <a href="{{ work.url | relative_url }}">
      <span class="list-mark">{{ work.work_type | escape }}</span>
      <h2>{{ work.title | escape }}</h2>
      <span class="list-meta">{% if author %}{{ author.name | escape }}{% endif %}</span>
    </a>
  </li>
  {% endfor %}
</ol>
