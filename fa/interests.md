---
layout: fa-page
title: علاقه‌مندی‌ها
permalink: /fa/interests/
---

# علاقه‌مندی‌ها

در کنار فعالیت‌های حرفه‌ای در فیزیک، فناوری و صنعت، موضوعات دیگری را نیز به‌صورت مستقل و با جدیت مطالعه و دنبال می‌کنم.

در این بخش، مقاله‌ها، یادداشت‌های مطالعاتی، منابع و مطالب مرتبط با این موضوعات را گردآوری می‌کنم.

<div class="interest-filters">

  <button class="interest-filter active" data-filter="all">
    <strong>همه</strong>
    <span>نمایش همه مطالب</span>
  </button>

  <button class="interest-filter" data-filter="ایران">
    <strong>ایران</strong>
    <span>تاریخ، جامعه، جغرافیا و فرهنگ</span>
  </button>

  <button class="interest-filter" data-filter="ترکمن‌ها">
    <strong>ترکمن‌ها</strong>
    <span>تاریخ، فرهنگ، مردم و آسیای مرکزی</span>
  </button>

  <button class="interest-filter" data-filter="زبان‌ها">
    <strong>زبان‌ها</strong>
    <span>زبان‌شناسی، ریشه‌شناسی و خط</span>
  </button>

  <button class="interest-filter" data-filter="حشره‌شناسی">
    <strong>حشره‌شناسی</strong>
    <span>حشرات، رده‌بندی، بوم‌شناسی و تکامل</span>
  </button>

  <button class="interest-filter" data-filter="کتاب">
    <strong>کتاب و نقد کتاب</strong>
    <span>کتاب‌ها، نقدها و یادداشت‌های مطالعاتی</span>
  </button>

</div>


{% assign interest_posts = site.posts | where: "lang", "fa" | where: "section", "interests" %}

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
      {{ post.date | date: "%Y/%m/%d" }}
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
      ادامه مطلب ←
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
