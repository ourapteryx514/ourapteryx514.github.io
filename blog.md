---
layout: clean-page
title: Blog
permalink: /blog/
---

# Daily Notes

Personal observations, photographs, reading notes, travel, science and other things I find worth recording.

{% for post in site.posts %}

## [{{ post.title }}]({{ post.url | relative_url }})

{{ post.date | date: "%d %B %Y" }}

{{ post.excerpt }}

[Read more →]({{ post.url | relative_url }})

---

{% endfor %}
