---
layout: default
title: "root@carlosmoreno:~$"
---

<pre class="ascii-logo">
 ██████╗███╗   ███╗
██╔════╝████╗ ████║
██║     ██╔████╔██║  
██║     ██║╚██╔╝██║  
╚██████╗██║ ╚═╝ ██║  [2026]
 ╚═════╝╚═╝     ╚═╝
</pre>

# [ SESSION STARTED: <span class="term-muted">{{ "now" | date: "%Y-%m-%d %H:%M" }}</span> ]

<span class="term-prompt">/</span><span class="term-cmd">novedades</span>

{% assign latest_post = site.posts.first %}

### > {{ latest_post.title | upcase }}
<div class="term-muted">DATE: {{ latest_post.date | date: "%d/%m/%Y" }}</div>

---

{% if latest_post.content contains '</h3>' %}
  {{ latest_post.content | split: '</h3>' | last }}
{% else %}
  {{ latest_post.content }}
{% endif %}

---

<span class="term-prompt">$</span> <span class="term-cmd">/recent_posts --limit 5</span>
{% for post in site.posts offset:1 limit:5 %}
* <span class="term-muted">{{ post.date | date: "%Y-%m-%d" }}</span> - [{{ post.title }}]({{ post.url }})
{% endfor %}

<br>

<span class="term-prompt">$</span> <span class="term-cmd">archive --access</span>
> [ Ver todos los registros del sistema ](/archive)

---

<span class="term-prompt">$</span> <span class="term-cmd">help --info</span>
> El sistema muestra el post más reciente. Usa /archive para el historial.

<span class="term-prompt">$</span> <span class="blink">_</span>
