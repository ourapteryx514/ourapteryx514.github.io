---
layout: home
title: Home
---

<div class="hero">

  <img src="{{ '/assets/images/profile.jpg' | relative_url }}"
       alt="Your Name"
       class="profile-photo">

  <div class="hero-text">

    <h1>OMID KOKABEE</h1>

    <p class="subtitle">
      Physicist · Photonics Researcher · Technology & Industry
    </p>

    <p>
      I am a physicist with a background in photonics, ultrafast lasers
      and optical parametric oscillators. My interests also extend into
      energy, industrial technology and international business.
    </p>

    <p>
      This website is where I collect my research, projects,
      professional interests and personal notes.
    </p>

  </div>

</div>

<div class="section-title">
  <h2>Explore</h2>
</div>

<div class="cards">

  <a class="card" href="{{ '/research/' | relative_url }}">
    <h3>Research</h3>
    <p>
      Photonics, ultrafast lasers, optical parametric oscillators
      and related scientific work.
    </p>
  </a>

  <a class="card" href="{{ '/projects/' | relative_url }}">
    <h3>Projects</h3>
    <p>
      Selected technical, industrial and interdisciplinary projects.
    </p>
  </a>

  <a class="card" href="{{ '/blog/' | relative_url }}">
    <h3>Daily Notes</h3>
    <p>
      Photographs, observations, books, travel, science and everyday notes.
    </p>
  </a>

</div>

<div class="section-title">
  <h2>Recent Notes</h2>
</div>

<div class="recent-notes">

{% for post in site.posts limit:3 %}

<div class="recent-note">

<h3>
<a href="{{ post.url | relative_url }}">{{ post.title }}</a>
</h3>

<p class="post-date">
{{ post.date | date: "%d %B %Y" }}
</p>

{{ post.excerpt }}

</div>

{% endfor %}

</div>
