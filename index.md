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

[$ /novedades
{% assign latest_post = site.posts.first %}
---
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
</style>
