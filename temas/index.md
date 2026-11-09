---
layout: page
title: Temas
description: Encuentra historias y ensayos de Ashogath por género, imaginario y asunto.
permalink: /temas/
---

Cada tema conduce a lecturas concretas, no a una etiqueta aislada.

<ul class="topic-list" aria-label="Temas disponibles">
  {% assign ordered_topics = site.topics | sort_natural: "title" %}
  {% for topic in ordered_topics %}
  <li><a href="{{ topic.url | relative_url }}">{{ topic.title | escape }}</a></li>
  {% endfor %}
</ul>

<h2>Lecturas</h2>
<ol class="reading-list">
  {% assign ordered_works = site.works | sort_natural: "order" %}
  {% for work in ordered_works %}
  {% assign author = site.authors | where: "slug", work.author | first %}
  <li>
    <a href="{{ work.url | relative_url }}">
      <span class="list-mark">{{ work.work_type | escape }}</span>
      <h3>{{ work.title | escape }}</h3>
      <span class="list-meta">{% if author %}{{ author.name | escape }}{% endif %}</span>
    </a>
  </li>
  {% endfor %}
</ol>
