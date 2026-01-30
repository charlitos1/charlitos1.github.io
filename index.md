---
layout: default
title: "root@carlosmoreno:~$"
---

<pre style="color: #00ff00; line-height: 1.1; font-size: 0.8em; border: none; background: transparent;">
 ██████╗███╗   ███╗
██╔════╝████╗ ████║
██║     ██╔████╔██║  [ REPOSITORY LOADED ]
██║     ██║╚██╔╝██║  [ ACCESS: GRANTED ]
╚██████╗██║ ╚═╝ ██║  [ VERSION: 2026.1 ]
 ╚═════╝╚═╝     ╚═╝
</pre>

# [ SESSION STARTED: {{ "now" | date: "%Y-%m-%d %H:%M" }} ]

[$ /novedades/fetch --latest
{% assign latest_post = site.posts.first %}
---
### > {{ latest_post.title | upcase }}
**DATE:** {{ latest_post.date | date: "%d/%m/%Y" }}
**STATUS:** VERIFIED_CONTENT

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

$ system_status --metrics
> **TRAFFIC_LOGS:** ![Visitas](https://visitor-badge.laobi.icu/badge?page_id=charlitos1.charlitos1.github.io&left_color=2d2d2d&right_color=00ff00)
> **PROMPT_STATUS:** IDLE
> **CURSOR:** _ <span class="blink">█</span>

<style>
  .blink { animation: blinker 1.2s linear infinite; color: #00ff00; }
  @keyframes blinker { 50% { opacity: 0; } }
  pre { overflow-x: hidden; white-space: pre-wrap; word-wrap: break-word; font-family: monospace; }
</style>
