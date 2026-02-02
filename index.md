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

