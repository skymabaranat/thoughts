---
layout: default
title: Trevs Drivel
---

# Trevs Drivel

Super cool thoughts of me.

---

## Blog Posts

{% for post in site.posts %}
- [{{ post.title }}]({{ post.url }}) - {{ post.date | date: "%B %d, %Y" }}
{% endfor %}
