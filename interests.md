---
layout: clean-page
title: Interests
permalink: /interests/
---

# INTERESTS

Beyond my professional work in physics, technology and industry, I study a number of subjects independently and in considerable depth.

This section brings together articles, reading notes, references and observations related to these interests.

<div class="interest-filters">

  <button class="interest-filter active" data-filter="all">
    <strong>All</strong>
    <span>View all interest articles</span>
  </button>

  <button class="interest-filter" data-filter="Iran">
    <strong>Iran</strong>
    <span>History, society, geography and culture</span>
  </button>

  <button class="interest-filter" data-filter="Turkmens">
    <strong>Turkmens</strong>
    <span>History, culture, peoples and Central Asia</span>
  </button>

  <button class="interest-filter" data-filter="Languages">
    <strong>Languages</strong>
    <span>Linguistics, etymology and writing systems</span>
  </button>

  <button class="interest-filter" data-filter="Entomology">
    <strong>Entomology</strong>
    <span>Insects, taxonomy, ecology and evolution</span>
  </button>

  <button class="interest-filter" data-filter="Books">
    <strong>Books & Reviews</strong>
    <span>Books, reviews and reading notes</span>
  </button>

</div>


{% assign interest_posts = site.posts | where: "lang", "en" | where: "section", "interests" %}

<div class="blog-list interest-articles">

{% for post in interest_posts %}

<article class="blog-entry interest-article"
         data-tags="{{ post.tags | join: '|' }}">

  {% if post.image %}
  <div>
    <img
      src="{{ post.image | relative_url }}"
      alt="{{ post.title | escape }}"
      style="width:220px; height:150px; object-fit:cover; border-radius:8px; display:block;">
  </div>
  {% endif %}

  <div class="blog-entry-content">

    <p class="blog-date">
      {{ post.date | date: "%d %B %Y" }}
    </p>

    {% if post.tags %}
    <p class="interest-tags">
      {% for tag in post.tags %}
        <span>{{ tag }}</span>
      {% endfor %}
    </p>
    {% endif %}

    <h2>
      <a href="{{ post.url | relative_url }}">
        {{ post.title }}
      </a>
    </h2>

    <div class="blog-excerpt">
      {{ post.excerpt }}
    </div>

    <a class="read-more" href="{{ post.url | relative_url }}">
      Read article →
    </a>

  </div>

</article>

{% endfor %}

</div>


<script>
document.addEventListener("DOMContentLoaded", function () {

  const filters = document.querySelectorAll(".interest-filter");
  const articles = document.querySelectorAll(".interest-article");

  filters.forEach(function (button) {

    button.addEventListener("click", function () {

      const selected = button.dataset.filter;

      filters.forEach(function (item) {
        item.classList.remove("active");
      });

      button.classList.add("active");

      articles.forEach(function (article) {

        const tags = article.dataset.tags.split("|");

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
