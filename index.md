---
layout: default
title: Home
permalink: /
---

<section class="hero">

  <img
    src="{{ '/assets/images/profile.jpeg' | relative_url }}"
    alt="Omid Kokabee"
    class="profile-photo">

  <div class="hero-text">

    <h1>OMID KOKABEE</h1>

    <p class="subtitle">
      Physicist · Technology & Industry Consultant · International Business & Trade
    </p>

    <p>
      I am a physicist with a background in photonics, ultrafast lasers
      and nonlinear optics, alongside professional activities in technology,
      industry, energy and international business.
    </p>

    <p>
      This website brings together my research, professional projects,
      independent interests and personal notes.
    </p>

  </div>

</section>


<!-- =====================================================
     MAIN SECTIONS
     ===================================================== -->

<div class="cards">

  <div class="card">

    <h3>
      <a href="{{ '/research/' | relative_url }}">
        Research
      </a>
    </h3>

    <p>
      Photonics, ultrafast lasers, nonlinear optics and optical parametric systems.
    </p>

  </div>


  <div class="card">

    <h3>
      <a href="{{ '/projects/' | relative_url }}">
        Projects
      </a>
    </h3>

    <p>
      Technology, energy, industrial materials and international business.
    </p>

  </div>


  <div class="card">

    <h3>
      <a href="{{ '/interests/' | relative_url }}">
        Interests
      </a>
    </h3>

    <p>
      Independent study in history, Turkmens, languages, entomology and books.
    </p>

  </div>


  <div class="card">

    <h3>
      <a href="{{ '/blog/' | relative_url }}">
        Blog
      </a>
    </h3>

    <p>
      Personal notes, photographs, memories, science, travel and observations.
    </p>

  </div>

</div>


<!-- =====================================================
     RECENT NOTES
     ===================================================== -->

<div class="section-title">

  <h2>Recent Notes</h2>

</div>


{% assign english_posts = site.posts | where: "lang", "en" %}

{% assign recent_posts = english_posts
   | where_exp: "post", "post.section != 'interests'" %}


<div class="recent-notes-grid">

  {% for post in recent_posts limit:4 %}

  <article class="recent-note-home">

    {% if post.image %}

    <a href="{{ post.url | relative_url }}">

      <img
        src="{{ post.image | relative_url }}"
        alt="{{ post.title | escape }}">

    </a>

    {% endif %}


    <div class="recent-note-text">

      <p class="post-date">
        {{ post.date | date: "%B %-d, %Y" }}
      </p>


      <h3>

        <a href="{{ post.url | relative_url }}">
          {{ post.title }}
        </a>

      </h3>


      {% if post.excerpt %}

      <div class="recent-note-excerpt">
        {{ post.excerpt }}
      </div>

      {% endif %}

    </div>

  </article>

  {% endfor %}

</div>
