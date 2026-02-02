---
layout: default
title: "root@carlosmoreno:~$"
---

<pre style="color: #00ff00; line-height: 1.1; font-size: 0.8em; border: none; background: transparent;">
 ██████╗███╗   ███╗
██╔════╝████╗ ████║
██║     ██╔████╔██║  
██║     ██║╚██╔╝██║  
╚██████╗██║ ╚═╝ ██║  [2026]
 ╚═════╝╚═╝     ╚═╝
</pre>

<h1 style="font-size: 1em;">[ SESSION STARTED: <span class="term-muted">{{ "now" | date: "%Y-%m-%d %H:%M" }}</span> ]</h1>

<span class="term-prompt">/</span><span class="term-cmd">novedades</span>
{% assign latest_post = site.posts.first %}

### > {{ latest_post.title | upcase }}
<span class="term-muted">DATE: {{ latest_post.date | date: "%d/%m/%Y" }}</span>

---

{{ latest_post.content }}

---

<span class="term-prompt">$</span> <span class="term-cmd">/recent_posts --limit 5</span>
{% for post in site.posts offset:1 limit:5 %}
* <span class="term-muted">{{ post.date | date: "%Y-%m-%d" }}</span> - [{{ post.title }}]({{ post.url }})
{% endfor %}

<br>

<span class="term-prompt">$</span> <span class="term-cmd">archive --access</span>
> [ <span class="term-cmd">Ver todos los registros del sistema (Full Archive)</span> ](/archive)

---

<span class="term-prompt">$</span> <span class="term-cmd">help --info</span>
<blockquote class="term-muted">
  El sistema muestra el post más reciente y los 5 anteriores.<br>
  Usa /archive para el historial completo.
</blockquote>

<span class="term-prompt">$</span> <span class="blink">_</span>

<style>
  /* Contenedor principal */
  body {
    background-color: #080808 !important; /* Negro más profundo */
    color: #d1d1d1;           /* Gris claro para el texto */
    font-family: 'Courier New', Courier, monospace;
    max-width: 720px;         /* Ancho de lectura óptimo */
    margin: 40px auto;
    line-height: 1.6;
    font-size: 18px;          /* Aumentamos el puntaje aquí */
    padding: 20px;
  }

  /* El Verde "Hacker" para comandos y acentos */
  .term-cmd, .blink, .term-prompt {
    color: #00ff00;
  }

  /* Título del Post: más grande y blanco puro para resaltar */
  h3 {
    color: #ffffff;
    font-size: 1.3em;
    margin-top: 1.5em;
    text-transform: uppercase;
  }

  /* Los links deben destacar */
  a {
    color: #00ff00;
    text-decoration: none;
  }

  a:hover {
    text-decoration: underline;
  }

  /* Datos secundarios (Date, Notas de ayuda) */
  .term-muted {
    color: #666;
  }

  pre { border: none; background: transparent; overflow: hidden; }
  .blink { animation: blinker 1.2s linear infinite; }
  @keyframes blinker { 50% { opacity: 0; } }
</style>
