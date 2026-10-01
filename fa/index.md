---
layout: fa-page
title: خانه
permalink: /fa/
---

<section class="hero">

  <img
    src="{{ '/assets/images/profile.jpeg' | relative_url }}"
    alt="امید کوکبی"
    class="profile-photo">

  <div class="hero-text">

    <h1>امید کوکبی</h1>

    <p class="subtitle">
      فیزیکدان · مشاور فناوری و صنعت · تجارت و کسب‌وکار بین‌المللی
    </p>

    <p>
      من فیزیکدان هستم و زمینه علمی من شامل فوتونیک، لیزرهای فوق‌سریع
      و اپتیک غیرخطی است. در کنار فعالیت‌های علمی، در حوزه‌های فناوری،
      صنعت، انرژی و تجارت بین‌المللی نیز فعالیت داشته‌ام.
    </p>

    <p>
      در این وب‌سایت بخشی از پژوهش‌ها، پروژه‌های حرفه‌ای،
      علاقه‌مندی‌های مستقل و یادداشت‌های شخصی‌ام را گردآوری می‌کنم.
    </p>

  </div>

</section>


<!-- =====================================================
     بخش‌های اصلی
     ===================================================== -->

<div class="cards">

  <div class="card">

    <h3>
      <a href="{{ '/fa/research/' | relative_url }}">
        پژوهش
      </a>
    </h3>

    <p>
      فوتونیک، لیزرهای فوق‌سریع، اپتیک غیرخطی و سامانه‌های پارامتری نوری.
    </p>

  </div>


  <div class="card">

    <h3>
      <a href="{{ '/fa/projects/' | relative_url }}">
        پروژه‌ها
      </a>
    </h3>

    <p>
      فناوری، انرژی، مواد صنعتی و تجارت بین‌المللی.
    </p>

  </div>


  <div class="card">

    <h3>
      <a href="{{ '/fa/interests/' | relative_url }}">
        علاقه‌مندی‌ها
      </a>
    </h3>

    <p>
      مطالعه مستقل در زمینه تاریخ، ترکمن‌ها، زبان‌ها، حشره‌شناسی و کتاب.
    </p>

  </div>


  <div class="card">

    <h3>
      <a href="{{ '/fa/blog/' | relative_url }}">
        وبلاگ
      </a>
    </h3>

    <p>
      یادداشت‌های شخصی، تصاویر، خاطرات، علم، سفر و مشاهدات.
    </p>

  </div>

</div>


<!-- =====================================================
     یادداشت‌های اخیر
     ===================================================== -->

<div class="section-title">

  <h2>یادداشت‌های اخیر</h2>

</div>


{% assign persian_posts = site.posts | where: "lang", "fa" %}

{% assign recent_posts = persian_posts
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
        {{ post.date | date: "%Y/%m/%d" }}
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
