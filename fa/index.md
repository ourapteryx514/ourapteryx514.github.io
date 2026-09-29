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
      فیزیکدان · پژوهشگر فوتونیک · فناوری و صنعت
    </p>

    <p>
      من فیزیکدانی با زمینه پژوهشی در فوتونیک، لیزرهای فوق‌سریع
      و نوسان‌سازهای پارامتری نوری هستم.
    </p>

    <p>
      علایق حرفه‌ای من همچنین حوزه‌های انرژی، فناوری صنعتی،
      تجارت بین‌المللی و پروژه‌های فنی را در بر می‌گیرد.
    </p>

  </div>

</div>


<div class="cards">

  <div class="card">
    <h3>
      <a href="{{ '/fa/research/' | relative_url }}">پژوهش</a>
    </h3>
    <p>
      فوتونیک، لیزرهای فوق‌سریع، اپتیک غیرخطی
      و فعالیت‌های علمی مرتبط.
    </p>
  </div>

  <div class="card">
    <h3>
      <a href="{{ '/fa/projects/' | relative_url }}">پروژه‌ها</a>
    </h3>
    <p>
      پروژه‌های علمی، فنی، صنعتی و میان‌رشته‌ای.
    </p>
  </div>

  <div class="card">
    <h3>
      <a href="{{ '/fa/blog/' | relative_url }}">وبلاگ</a>
    </h3>
    <p>
      یادداشت‌ها، تصاویر، کتاب‌ها، سفر، علم
      و مشاهدات روزمره.
    </p>
  </div>

</div>


<div class="section-title">
  <h2>آخرین یادداشت‌ها</h2>
</div>


{% assign persian_posts = site.posts | where: "lang", "fa" %}

<div class="recent-notes">

{% for post in persian_posts limit:3 %}

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
