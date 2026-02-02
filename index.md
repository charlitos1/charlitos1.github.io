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
  .blink { animation: blinker 1.2s linear infinite; color: #00ff00; }
  @keyframes blinker { 50% { opacity: 0; } }
  pre { overflow-x: hidden; white-space: pre-wrap; word-wrap: break-word; font-family: monospace; }

<style>
  /* Base de la Terminal */
  body {
    background-color: #0a0a0a; /* Negro profundo */
    color: #bbb;               /* Texto general gris suave para no cansar */
    font-family: 'Courier New', Courier, monospace;
    max-width: 700px;
    margin: 40px auto;
    padding: 20px;
    line-height: 1.6;
    font-size: 17px;           /* Subimos el puntaje para legibilidad */
  }

  /* Los comandos del sistema en Verde */
  h1, .command, .blink {
    color: #00ff00;
    font-size: 1em;
  }

  /* El Título del Post (Resaltado) */
  h3 {
    color: #fff;
    font-size: 1.4em;
    border-bottom: 1px solid #333;
    padding-bottom: 10px;
  }

  /* Enlaces estilo terminal */
  a {
    color: #00ff00;
    text-decoration: none;
  }
  
  a:hover {
    background: #00ff00;
    color: #000;
  }

  /* El cursor parpadeante */
  .blink { animation: blinker 1s linear infinite; }
  @keyframes blinker { 50% { opacity: 0; } }

  pre { overflow-x: hidden; white-space: pre-wrap; font-family: monospace; }
</style>
 
</style>
