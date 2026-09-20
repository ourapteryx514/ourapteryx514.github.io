---
layout: home
title: Home
---

<div class="hero">

  <img src="{{ '/assets/images/profile.jpeg' | relative_url }}"
       alt="OMID KOKABEE"
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

  <div class="card">
    <h3>
      <a href="{{ '/research/' | relative_url }}">Research</a>
    </h3>
    <p>
      Photonics, ultrafast lasers, optical parametric oscillators
      and related scientific work.
    </p>
  </div>

  <div class="card">
    <h3>
      <a href="{{ '/projects/' | relative_url }}">Projects</a>
    </h3>
    <p>
      Selected technical, industrial and interdisciplinary projects.
    </p>
  </div>

  <div class="card">
    <h3>
      <a href="{{ '/blog/' | relative_url }}">Daily Notes</a>
    </h3>
    <p>
      Photographs, observations, books, travel, science and everyday notes.
    </p>
  </div>

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
