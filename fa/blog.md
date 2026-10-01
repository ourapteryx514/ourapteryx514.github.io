---
layout: fa-page
title: وبلاگ
permalink: /fa/blog/
---

<div class="content-page blog-page">

  <!-- =====================================================
       HERO
       ===================================================== -->

  <section class="page-hero blog-hero">

    <p class="page-kicker">وبلاگ</p>

    <h1>
      یادداشت‌ها
    </h1>

    <div class="page-focus">
      <span>یادداشت‌های شخصی</span>
      <span>علم</span>
      <span>کتاب</span>
      <span>سفر</span>
      <span>تصاویر</span>
    </div>

  </section>


  <!-- =====================================================
       POSTS
       ===================================================== -->

  <section class="page-section page-section-last blog-section">

    {% assign persian_posts = site.posts | where: "lang", "fa" %}
    {% assign blog_posts = persian_posts
       | where_exp: "post", "post.section != 'interests'" %}

    <div class="blog-library">

      {% for post in blog_posts %}

      <article class="blog-library-item{% unless post.image %} no-image{% endunless %}">

        {% if post.image %}

        <a
          class="blog-library-image"
          href="{{ post.url | relative_url }}">

          <img
            src="{{ post.image | relative_url }}"
            alt="{{ post.image_caption | default: post.title | escape }}">

        </a>

        {% endif %}


        <div class="blog-library-content">

          <!-- META -->

          <div class="blog-library-meta">

            <span class="blog-library-date">
              {{ post.date | date: "%Y/%m/%d" }}
            </span>


            {% if post.categories %}

            <div class="blog-library-categories">

              {% for category in post.categories %}
                <span>{{ category }}</span>
              {% endfor %}

            </div>

            {% endif %}

          </div>


          <!-- TITLE -->

          <h3>
            <a href="{{ post.url | relative_url }}">
              {{ post.title }}
            </a>
          </h3>


          <!-- EXCERPT -->

          <div class="blog-library-excerpt">
            {{ post.excerpt }}
          </div>


          <!-- LINK -->

          <a
            class="blog-library-link"
            href="{{ post.url | relative_url }}">
            ادامه مطلب ←
          </a>

        </div>

      </article>

      {% endfor %}

    </div>

  </section>

</div>
