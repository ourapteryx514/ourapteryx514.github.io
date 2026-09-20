---
layout: clean-page
title: Blog
permalink: /blog/
---

# BLOG

---
layout: clean-page
title: Blog
permalink: /blog/
---

# BLOG

<p class="blog-intro">
Personal notes, photographs, books, travel, science, technology and observations from everyday life.
</p>

<div class="blog-list">

{% for post in site.posts %}

<article class="blog-entry">

  {% if post.image %}
  <a href="{{ post.url | relative_url }}">
    <img
      src="{{ post.image | relative_url }}"
      alt="{{ post.title }}"
      class="blog-thumbnail">
  </a>
  {% endif %}

  <div class="blog-entry-content">

    <p class="blog-date">
      {{ post.date | date: "%d %B %Y" }}
    </p>

    <h2>
      <a href="{{ post.url | relative_url }}">
        {{ post.title }}
      </a>
    </h2>

    <div class="blog-excerpt">
      {{ post.excerpt }}
    </div>

    <a class="read-more" href="{{ post.url | relative_url }}">
      Read more →
    </a>

  </div>

</article>

{% endfor %}

</div>
