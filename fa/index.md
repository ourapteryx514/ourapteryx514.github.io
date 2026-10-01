---
layout: fa-page
title: فارسی
permalink: /fa/
---

<div class="hero">

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
      من فیزیکدانی با پیشینه پژوهشی در فوتونیک، لیزرهای فوق‌سریع و اپتیک غیرخطی هستم. در کنار فعالیت‌های علمی، در حوزه‌های فناوری، صنعت و کسب‌وکار بین‌المللی نیز فعالیت دارم و تجربه‌ام شامل مشاوره فنی، پروژه‌های صنعتی، تجارت فرامرزی، تأمین کالا و هماهنگی‌های تجاری است.
    </p>

    <p>
      این وب‌سایت مجموعه‌ای از پژوهش‌ها، فعالیت‌های حرفه‌ای، پروژه‌های فنی، علایق من در تجارت بین‌المللی و یادداشت‌های شخصی‌ام را در بر می‌گیرد.
    </p>

  </div>

</div>


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

<div class="section-title">
  <h2>آخرین یادداشت‌ها</h2>
</div>

{% assign persian_posts = site.posts | where: "lang", "fa" %}
{% assign recent_posts = persian_posts | where_exp: "post", "post.section != 'interests'" %}

<div class="recent-notes">

{% for post in recent_posts limit:3 %}

  <div class="recent-note-home">

    {% if post.image %}
    <div>
      <img
        src="{{ post.image | relative_url }}"
        alt="{{ post.title | escape }}"
        style="width:180px; height:120px; object-fit:cover; border-radius:8px; display:block;">
    </div>
    {% endif %}

    <div class="recent-note-text">

      <p class="post-date">
        {{ post.date | date: "%Y/%m/%d" }}
      </p>

      {% if post.categories %}
      <p style="font-size:13px; color:#777; margin:4px 0 8px;">
        {% for category in post.categories %}
          <span style="
            display:inline-block;
            padding:3px 9px;
            margin-left:5px;
            border:1px solid #ddd;
            border-radius:14px;">
            {{ category }}
          </span>
        {% endfor %}
      </p>
      {% endif %}

      <h3>
        <a href="{{ post.url | relative_url }}">
          {{ post.title }}
        </a>
      </h3>

      <div>
        {{ post.excerpt }}
      </div>

      <a href="{{ post.url | relative_url }}">
        ادامه مطلب ←
      </a>

    </div>

  </div>

{% endfor %}

</div>
