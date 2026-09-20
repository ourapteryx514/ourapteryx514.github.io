---
layout: home
title: Home
---

# OMID KOKABEE

**Physicist · Photonics Researcher · Technology & Industry**

I am a physicist with a background in photonics, ultrafast lasers and optical parametric oscillators. My work and interests also extend into energy, industrial technology and international business.

This website is where I collect my research, projects, professional interests and personal notes.

## Explore

### [Research](/research/)
Academic work, photonics, lasers, optical parametric oscillators and selected technical topics.

### [Projects](/projects/)
Technical, industrial and interdisciplinary projects.

### [Daily Notes](/blog/)
Personal observations, photographs, reading notes, travel, science and everyday ideas.

## Recent Notes

{% for post in site.posts limit:3 %}

### [{{ post.title }}]({{ post.url | relative_url }})

{{ post.date | date: "%d %B %Y" }}

{{ post.excerpt }}

{% endfor %}
