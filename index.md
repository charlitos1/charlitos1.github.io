---
layout: default
title: "root@carlosmoreno:~$"
---

# [ LOG_START: {{ "now" | date: "%Y-%m-%d" }} ]

<div class="amodei-style">

{% assign latest_post = site.posts.first %}
<section class="latest">
  <span class="command">$ /novedades/read --latest</span>
  
  <h1 class="post-title">{{ latest_post.title }}</h1>
  <p class="post-meta">DATE: {{ latest_post.date | date: "%B %d, %Y" }} | STATUS: PUBLIC</p>
  
  <article class="content">
    {{ latest_post.content }}
  </article>
</section>

<hr class="system-divider">

<section class="history">
  <span class="command">$ /history --view-all</span>
  <ul class="post-list">
    {% for post in site.posts offset:1 limit:5 %}
    <li>
      <span class="date">{{ post.date | date: "%Y-%m-%d" }}</span> — 
      <a href="{{ post.url }}">{{ post.title }}</a>
    </li>
    {% endfor %}
  </ul>
</section>

</div>

<footer class="system-footer">
  <span class="command">$ system_info</span>
  <p>
    VISITORS: ![Visitas](https://visitor-badge.laobi.icu/badge?page_id=charlitos1.charlitos1.github.io&left_color=1a1a1a&right_color=00ff00) | 
    STATUS: IDLE <span class="blink">█</span>
  </p>
</footer>

<style>
  /* Inspiración Amodei: Tipografía y Espaciado */
  .amodei-style {
    max-width: 700px; /* Ancho de lectura óptimo como el de Dario */
    margin: 0 auto;
    line-height: 1.7;
    font-family: "Georgia", serif; /* Fuente de lectura para el cuerpo */
    color: #e0e0e0;
  }

  .command {
    display: block;
    font-family: monospace;
    color: #00ff00;
    margin-bottom: 10px;
    font-size: 0.9em;
  }

  .post-title {
    font-family: monospace; /* Mantiene el toque tech en el título */
    font-size: 1.8em;
    color: #ffffff;
    text-transform: uppercase;
    margin-top: 5px;
  }

  .post-meta {
    font-family: monospace;
    font-size: 0.8em;
    color: #888;
    margin-bottom: 30px;
  }

  .system-divider { border: 0; border-top: 1px solid #333; margin: 40px 0; }

  .post-list { list-style: none; padding: 0; font-family: monospace; }
  .post-list li { margin-bottom: 8px; }
  .post-list a { color: #00ff00; text-decoration: none; }
  .post-list a:hover { text-decoration: underline; }

  .blink { animation: blinker 1.2s linear infinite; }
  @keyframes blinker { 50% { opacity: 0; } }
</style>
