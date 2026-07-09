---
layout: page
title: Gallery
description: Photos from travel, landscapes, and everyday life outside research.
permalink: /gallery/
nav: false
nav_order: 6
---

{% assign photos = site.data.gallery.photos %}
{% assign categories = photos | map: "category" | uniq %}

<div class="life-gallery">
  {% if site.data.gallery.intro %}
    <p class="life-gallery-intro">{{ site.data.gallery.intro }}</p>
  {% endif %}

  <div class="life-gallery-filters" role="tablist" aria-label="Gallery categories">
    <button type="button" class="life-filter active" data-filter="all">All</button>
    {% for category in categories %}
      <button type="button" class="life-filter" data-filter="{{ category | slugify }}">{{ category }}</button>
    {% endfor %}
  </div>

  <div class="life-gallery-grid">
    {% for photo in photos %}
      <figure class="life-gallery-item" data-category="{{ photo.category | slugify }}">
        <a href="{{ photo.file | prepend: '/assets/img/' | relative_url }}" class="life-gallery-link">
          <img
            src="{{ photo.file | prepend: '/assets/img/' | relative_url }}"
            alt="{{ photo.title }}"
            loading="lazy"
            data-zoomable
          >
        </a>
        <figcaption>
          <span class="life-gallery-title">{{ photo.title }}</span>
          {% if photo.caption %}
            <span class="life-gallery-caption">{{ photo.caption }}</span>
          {% endif %}
        </figcaption>
      </figure>
    {% endfor %}
  </div>
</div>

<script>
  document.addEventListener("DOMContentLoaded", function () {
    var filters = document.querySelectorAll(".life-filter");
    var items = document.querySelectorAll(".life-gallery-item");

    filters.forEach(function (button) {
      button.addEventListener("click", function () {
        var filter = button.getAttribute("data-filter");

        filters.forEach(function (b) {
          b.classList.remove("active");
        });
        button.classList.add("active");

        items.forEach(function (item) {
          var category = item.getAttribute("data-category");
          var show = filter === "all" || category === filter;
          item.classList.toggle("is-hidden", !show);
        });
      });
    });
  });
</script>
