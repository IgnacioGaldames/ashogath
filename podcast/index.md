---
layout: page
title: Podcast
description: Espacio propio para futuras conversaciones y episodios de la Logia Ashogath.
permalink: /podcast/
---

Este espacio está reservado para el podcast de la Logia Ashogath. Cuando haya episodios publicados, cada uno tendrá su propia página, reproductor o enlace de escucha y una transcripción o notas para acompañarlo.

{% if site.podcast.size > 0 %}
<ol class="reading-list">
  {% assign episodes = site.podcast | sort_natural: "date" | reverse %}
  {% for episode in episodes %}
  <li>
    <a href="{{ episode.url | relative_url }}">
      <span class="list-mark">{% if episode.season %}{{ episode.season | escape }}{% else %}Episodio{% endif %}</span>
      <h2>{{ episode.title | escape }}</h2>
      <span class="list-meta">{% if episode.date %}{{ episode.date | date: "%d.%m.%Y" }}{% else %}Disponible{% endif %}</span>
    </a>
  </li>
  {% endfor %}
</ol>
{% else %}
<p class="empty-note">Aún no hay episodios publicados. La sección está preparada para crecer sin anunciar contenido que todavía no existe.</p>
{% endif %}
