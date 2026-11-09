---
layout: page
title: Blog
description: Novedades, conversaciones y textos de la Logia Ashogath.
permalink: /blog/
---

El blog es el espacio para novedades y textos del círculo; cada entrada puede enlazar con lecturas y autores de la revista.

{% if site.posts.size > 0 %}
<ol class="reading-list">
  {% for post in site.posts %}
  <li>
    <a href="{{ post.url | relative_url }}">
      <span class="list-mark">{{ post.date | date: "%d.%m.%Y" }}</span>
      <h2>{{ post.title | escape }}</h2>
      <span class="list-meta">{{ post.author | escape }}</span>
    </a>
  </li>
  {% endfor %}
</ol>
{% else %}
<p class="empty-note">Todavía no hay entradas publicadas. El archivo editorial se actualizará cuando el círculo publique nuevas noticias.</p>
{% endif %}
