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

# [ session started: <span class="term-muted">{{ "now" | date: "%Y-%m-%d %H:%M" }}</span> ]

<span class="term-prompt">/</span><span class="term-cmd">novedades</span>

{% assign latest_post = site.posts.first %}

<header style="margin-top: 20px;">
  <span class="term-muted">/entries/view --id="{{ latest_post.title | slugify }}"</span>
  <h3 style="margin-top: 10px;">> {{ latest_post.title }}</h3>
  <div class="term-muted" style="font-size: 0.8em;">
    date: {{ latest_post.date | date: "%d/%m/%Y" }}
  </div>
</header>

---

{{ latest_post.content }}

---

<span class="term-prompt">$</span> <span class="term-cmd">/recent_posts --limit 5</span>
{% for post in site.posts offset:1 limit:5 %}
* <span class="term-muted">{{ post.date | date: "%Y-%m-%d" }}</span> - [{{ post.title }}]({{ post.url }})
{% endfor %}

<br>

<span class="term-prompt">$</span> <span class="term-cmd">archive --access</span>
> [ ver todos los registros del sistema ](/archive)

---

<span class="term-prompt">$</span> <span class="term-cmd">help --info</span>
> el sistema muestra el post más reciente. usa /archive para el historial.

<span class="term-prompt">$</span> <span class="blink">_</span>
