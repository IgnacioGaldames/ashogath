---
layout: page
title: Fanzine
description: Ediciones de la revista Ashogath con descarga y acceso directo a cada cuento y ensayo.
permalink: /fanzines/
---

Cada edición conserva su lugar en la revista y abre una ruta directa a sus obras y autores.

<ol class="reading-list">
  {% assign ordered_issues = site.issues | sort_natural: "issue_number" %}
  {% for issue in ordered_issues %}
  <li>
    <a href="{{ issue.url | relative_url }}">
      <span class="list-mark">N.º {{ issue.issue_number }}</span>
      <h2>{{ issue.title | escape }}</h2>
      <span class="list-meta">{{ issue.theme | escape }}</span>
    </a>
  </li>
  {% endfor %}
</ol>
