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
<div>
  <a href="{{ post.url | relative_url }}"><img src="{{ post.image | relative_url }}" alt="{{ post.title | escape }}" style="width:220px; height:150px; object-fit:cover; border-radius:8px; display:block;"></a>
</div>
{% endif %}

  <div class="blog-entry-content">

    <p class="blog-date">
      {{ post.date | date: "%d %B %Y" }}
    </p>

{% if post.categories %}
<p style="font-size:13px; color:#777; margin:4px 0 8px;">
  {% for category in post.categories %}
    <span style="display:inline-block; padding:3px 9px; margin-right:5px; border:1px solid #ddd; border-radius:14px;">
      {{ category }}
    </span>
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
      Read more →
    </a>

  </div>

</article>

{% endfor %}

</div>
