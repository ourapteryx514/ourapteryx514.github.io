---
layout: fa-page
title: علاقه‌مندی‌ها
permalink: /fa/interests/
---

<div class="content-page interests-page">

  <!-- =====================================================
       HERO
       ===================================================== -->

  <section class="page-hero interests-hero">

    <p class="page-kicker">علاقه‌مندی‌ها</p>

    <h1>
      مطالعه مستقل، کتاب‌خوانی و موضوعاتی که در بلندمدت دنبال می‌کنم.
    </h1>

    <p class="page-lead">
      در کنار فعالیت‌های حرفه‌ای در علم، فناوری و صنعت،
      موضوعات دیگری را نیز به‌صورت مستقل و با جدیت دنبال می‌کنم.
      این بخش مجموعه‌ای از
      <strong>مقاله‌ها، یادداشت‌های مطالعاتی، منابع و مشاهدات</strong>
      مرتبط با این حوزه‌هاست.
    </p>

    <div class="page-focus">
      <span>ایران</span>
      <span>ترکمن‌ها</span>
      <span>زبان‌ها</span>
      <span>حشره‌شناسی</span>
      <span>کتاب و نقد کتاب</span>
    </div>

  </section>


  <!-- =====================================================
       SUBJECT FILTERS
       ===================================================== -->

  <section class="page-section interests-section">

    <div class="section-heading">

      <p class="section-number">۰۱</p>

      <div>
        <h2>مرور بر اساس موضوع</h2>
        <p>
          مطالب را بر اساس موضوع مورد نظر خود فیلتر کنید.
        </p>
      </div>

    </div>


    <div class="interest-filter-bar">

      <button
        class="interest-filter-chip active"
        data-filter="all">
        همه
      </button>

      <button
        class="interest-filter-chip"
        data-filter="ایران">
        ایران
      </button>

      <button
        class="interest-filter-chip"
        data-filter="ترکمن‌ها">
        ترکمن‌ها
      </button>

      <button
        class="interest-filter-chip"
        data-filter="زبان‌ها">
        زبان‌ها
      </button>

      <button
        class="interest-filter-chip"
        data-filter="حشره‌شناسی">
        حشره‌شناسی
      </button>

      <button
        class="interest-filter-chip"
        data-filter="کتاب">
        کتاب و نقد کتاب
      </button>

    </div>

  </section>


  <!-- =====================================================
       ARTICLES
       ===================================================== -->

  <section class="page-section page-section-last interests-section">

    <div class="section-heading">

      <p class="section-number">۰۲</p>

      <div>
        <h2>مقاله‌ها و یادداشت‌ها</h2>
        <p>
          مقاله‌ها، یادداشت‌های پژوهشی، یادداشت‌های مطالعاتی و بررسی منابع.
        </p>
      </div>

    </div>


    {% assign interest_posts = site.posts
       | where: "lang", "fa"
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
              {{ post.date | date: "%Y/%m/%d" }}
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
            ادامه مطلب ←
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
