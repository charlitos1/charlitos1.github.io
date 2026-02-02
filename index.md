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

# [ SESSION STARTED: {{ "now" | date: "%Y-%m-%d %H:%M" }} ]

/novedades
{% assign latest_post = site.posts.first %}

### > {{ latest_post.title | upcase }}
**DATE:** {{ latest_post.date | date: "%d/%m/%Y" }}


---

{{ latest_post.content }}

---

$ /recent_posts --limit 5
{% for post in site.posts offset:1 limit:5 %}
* {{ post.date | date: "%Y-%m-%d" }} - [{{ post.title }}]({{ post.url }})
{% endfor %}



$ archive --access
> [ Ver todos los registros del sistema (Full Archive) ](/archive)

---

$ help --info
> El sistema muestra el post más reciente y los 5 anteriores.
> Usa /archive para el historial completo.

---


<style>
   
  /* Contenedor principal */
  body {
    background-color: #080808 !important; /* Negro más profundo */
    color: #d1d1d1;           /* Gris claro para el texto (menos agresivo que el blanco) */
    font-family: 'Courier New', Courier, monospace;
    max-width: 720px;         /* Ancho de lectura óptimo */
    margin: 40px auto;
    line-height: 1.6;
    font-size: 18px;          /* Aumentamos el puntaje aquí */
  }

  /* El Verde "Hacker" para comandos y acentos */
  .term-cmd, .blink, .term-prompt {
    color: #00ff00;
    font-weight: bold;
  }

  /* Título del Post: más grande y blanco puro para resaltar */
  h3 {
    color: #ffffff;
    font-size: 1.3em;
    margin-top: 1.5em;
    text-transform: uppercase;
  }

  /* Los links deben destacar en la oscuridad */
  a {
    color: #00ff00;
    text-decoration: none;
    border-bottom: 1px solid transparent;
  }

  a:hover {
    border-bottom: 1px solid #00ff00;
  }

  /* Datos secundarios (Date, Autor) */
  .term-muted {
    color: #666;
    font-size: 0.9em;
  }

  pre { border: none; background: transparent; overflow: hidden; }
  .blink { animation: blinker 1.2s linear infinite; }
  @keyframes blinker { 50% { opacity: 0; } }
</style>

