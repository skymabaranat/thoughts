---
layout: default
title: Trevs Drivel
---

# Trevs Drivel

Super cool thoughts of me.

---

## Blog Posts

<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a> - {{ post.date | date: "%B %d, %Y" }}
    </li>
  {% endfor %}
</ul>
