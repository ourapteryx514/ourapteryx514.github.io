---
layout: clean-page
title: Interests
permalink: /interests/
---

<div class="content-page interests-page">

  <!-- =====================================================
       HERO
       ===================================================== -->

  <section class="page-hero interests-hero">

    <p class="page-kicker">INTERESTS</p>

    <h1>
      Independent study, reading and long-term intellectual interests.
    </h1>

    <p class="page-lead">
      Beyond my professional work in science, technology and industry,
      I study a number of subjects independently and in considerable depth.
      This section brings together
      <strong>articles, reading notes, references and observations</strong>
      developed around those interests.
    </p>

    <div class="page-focus">
      <span>Iran</span>
      <span>Turkmens</span>
      <span>Languages</span>
      <span>Entomology</span>
      <span>Books & Reviews</span>
    </div>

  </section>


  <!-- =====================================================
       SUBJECT FILTERS
       ===================================================== -->

  <section class="page-section interests-section">

    <div class="section-heading">

      <p class="section-number">01</p>

      <div>
        <h2>Browse by Subject</h2>
        <p>
          Filter the articles according to the subjects you are interested in.
        </p>
      </div>

    </div>


    <div class="interest-filter-bar">

      <button
        class="interest-filter-chip active"
        data-filter="all">
        All
      </button>

      <button
        class="interest-filter-chip"
        data-filter="Iran">
        Iran
      </button>

      <button
        class="interest-filter-chip"
        data-filter="Turkmens">
        Turkmens
      </button>

      <button
        class="interest-filter-chip"
        data-filter="Languages">
        Languages
      </button>

      <button
        class="interest-filter-chip"
        data-filter="Entomology">
        Entomology
      </button>

      <button
        class="interest-filter-chip"
        data-filter="Books">
        Books & Reviews
      </button>

    </div>

  </section>


  <!-- =====================================================
       ARTICLES
       ===================================================== -->

  <section class="page-section page-section-last interests-section">

    <div class="section-heading">

      <p class="section-number">02</p>

      <div>
        <h2>Articles & Notes</h2>
        <p>
          Essays, research notes, reading notes and source-based explorations.
        </p>
      </div>

    </div>


    {% assign interest_posts = site.posts
       | where: "lang", "en"
       | where: "section", "interests" %}


    <div class="interest-library">

      {% for post in interest_posts %}

      <article
        class="interest-library-item{% unless post.image %} no-image{% endunless %}"
        data-tags="{{ post.tags | join: '|' }}">

        {% if post.image %}

        <a
          class="interest-library-image"
          href="{{ post.url | relative_url }}">

          <img
            src="{{ post.image | relative_url }}"
            alt="{{ post.title | escape }}">

        </a>

        {% endif %}


        <div class="interest-library-content">

          <div class="interest-library-meta">

            <span class="interest-library-date">
              {{ post.date | date: "%d %B %Y" }}
            </span>

            {% if post.tags %}

            <div class="interest-library-tags">

              {% for tag in post.tags %}
                <span>{{ tag }}</span>
              {% endfor %}

            </div>

            {% endif %}

          </div>


          <h3>
            <a href="{{ post.url | relative_url }}">
              {{ post.title }}
            </a>
          </h3>


          <div class="interest-library-excerpt">
            {{ post.excerpt }}
          </div>


          <a
            class="interest-library-link"
            href="{{ post.url | relative_url }}">
            Read article →
          </a>

        </div>

      </article>

      {% endfor %}

    </div>

  </section>

</div>


<script>
document.addEventListener("DOMContentLoaded", function () {

  const filters = document.querySelectorAll(".interest-filter-chip");
  const articles = document.querySelectorAll(".interest-library-item");

  filters.forEach(function (button) {

    button.addEventListener("click", function () {

      const selected = button.dataset.filter;

      filters.forEach(function (item) {
        item.classList.remove("active");
      });

      button.classList.add("active");

      articles.forEach(function (article) {

        const tags = article.dataset.tags
          ? article.dataset.tags.split("|")
          : [];

        if (selected === "all" || tags.includes(selected)) {
          article.style.display = "";
        } else {
          article.style.display = "none";
        }

      });

    });

  });

});
</script>
