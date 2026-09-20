---
layout: clean-page
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
      <a href="{{ '/blog/' | relative_url }}">Blog</a>
    </h3>
    <p>
      Personal notes, photographs, books, travel, science and everyday observations.
    </p>
  </div>

</div>


<div class="section-title">
  <h2>Recent Notes</h2>
</div>

<div class="recent-notes">

{% for post in site.posts limit:3 %}

  <div class="recent-note-home">

    {% if post.image %}
    <div>
      <a href="{{ post.url | relative_url }}">
        <img
          src="{{ post.image | relative_url }}"
          alt="{{ post.title | escape }}"
          style="width:180px; height:120px; object-fit:cover; border-radius:8px; display:block;">
      </a>
    </div>
    {% endif %}

    <div class="recent-note-text">

      <p class="post-date">
        {{ post.date | date: "%d %B %Y" }}
      </p>

      <h3>
        <a href="{{ post.url | relative_url }}">
          {{ post.title }}
        </a>
      </h3>

      <div>
        {{ post.excerpt }}
      </div>

      <a href="{{ post.url | relative_url }}">
        Read more →
      </a>

    </div>

  </div>

{% endfor %}

</div>
