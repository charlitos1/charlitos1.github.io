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

[$ /novedades/fetch --latest
{% assign latest_post = site.posts.first %}
---
### > {{ latest_post.title | upcase }}
**DATE:** {{ latest_post.date | date: "%d/%m/%Y" }}


---

{{ latest_post.content }}

---

$ /recent_posts --limit 5
<pre class="terminal-history">
{% for post in site.posts offset:1 limit:5 %}
* {{ post.date | date: "%Y-%m-%d" }} - <a href="{{ post.url }}">{{ post.title }}</a>
{% endfor %}
</pre>


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

.terminal-history {
    background: transparent; /* Quita el fondo gris que ponen algunos temas */
    border: none;           /* Quita bordes */
    padding: 0;
    margin: 0;
    color: inherit;         /* Mantiene el color verde o blanco de tu terminal */
    font-family: monospace;
    line-height: 1.2;       /* Aquí controlas el interlineado exacto */
    overflow: hidden;       /* Evita barras de desplazamiento */
}

.terminal-history a {
    color: #00ff00;         /* El color de tus links */
    text-decoration: none;
}

.terminal-history a:hover {
    text-decoration: underline;
}

</style>
