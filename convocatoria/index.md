---
layout: page
title: Convocatoria
description: Estado y condiciones para recibir cuentos para el próximo fanzine de la Logia Ashogath.
permalink: /convocatoria/
---

La próxima edición empieza con una voz que todavía no está en la revista. Esta página mantiene visible el estado real de la convocatoria y sus condiciones se pueden actualizar en un solo archivo.

<section class="call-panel" aria-labelledby="call-status-heading">
  {% if site.data.convocatoria.status == "open" %}
  <p class="call-status call-status--open">Convocatoria abierta</p>
  <h2 id="call-status-heading">Estamos leyendo nuevas propuestas.</h2>
  {% if site.data.convocatoria.guidelines %}
  <p>{{ site.data.convocatoria.guidelines | escape }}</p>
  {% endif %}
  {% else %}
  <p class="call-status call-status--closed">Convocatoria cerrada</p>
  <h2 id="call-status-heading">Por ahora no estamos recibiendo cuentos.</h2>
  <p>La convocatoria se abrirá cuando estén definidas las condiciones del próximo fanzine. No envíes trabajos todavía.</p>
  {% endif %}

  <dl class="call-details">
    <div>
      <dt>Tema</dt>
      <dd>{% if site.data.convocatoria.theme != "" %}{{ site.data.convocatoria.theme | escape }}{% else %}Por definir{% endif %}</dd>
    </div>
    <div>
      <dt>Plazo</dt>
      <dd>{% if site.data.convocatoria.deadline != "" %}{{ site.data.convocatoria.deadline | escape }}{% else %}Por definir{% endif %}</dd>
    </div>
    <div>
      <dt>Envío</dt>
      <dd>
        {% if site.data.convocatoria.submission_email != "" %}
          <a href="mailto:{{ site.data.convocatoria.submission_email | escape }}">{{ site.data.convocatoria.submission_email | escape }}</a>
        {% elsif site.data.convocatoria.submission_url != "" %}
          <a href="{{ site.data.convocatoria.submission_url | escape }}">{{ site.data.convocatoria.submission_url | escape }}</a>
        {% else %}
          Por definir
        {% endif %}
      </dd>
    </div>
  </dl>
</section>

<p>Para consultar futuras bases o preguntar por la próxima edición, puedes escribir a <a href="{{ site.data.convocatoria.contact_url | escape }}" target="_blank" rel="noopener noreferrer">Logia Ashogath en Instagram</a>. Ese canal es solo de consulta: no sustituye un correo o formulario de envío que aún no se ha anunciado.</p>
