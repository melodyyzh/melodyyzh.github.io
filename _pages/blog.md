---
layout: default
permalink: /blog/
title: Blog
nav: true
nav_order: 6
pagination:
  enabled: true
  collection: posts
  permalink: /page/:num/
  per_page: 10
  sort_field: date
  sort_reverse: true
  trail:
    before: 1
    after: 3
---

<div class="post">
  <header class="post-header">
    <h1 class="post-title">{{ page.title }}</h1>
    {% if site.blog_description and site.blog_description != "" %}
      <p class="post-description">{{ site.blog_description }}</p>
    {% endif %}
  </header>

  <ul class="post-list simple-blog-list">
    {% if page.pagination.enabled %}
      {% assign postlist = paginator.posts %}
    {% else %}
      {% assign postlist = site.posts %}
    {% endif %}

    {% for post in postlist %}
      <li class="simple-blog-item">
        {% if post.thumbnail %}
          <div class="row align-items-center">
            <div class="col-sm-9">
        {% endif %}

        <h3>
          <a class="post-title" href="{{ post.url | relative_url }}">{{ post.title }}</a>
        </h3>

        {% if post.description %}
          <p>{{ post.description }}</p>
        {% endif %}

        <p class="post-meta">{{ post.date | date: "%B %d, %Y" }}</p>

        {% if post.thumbnail %}
            </div>
            <div class="col-sm-3">
              <a href="{{ post.url | relative_url }}">
                <img
                  class="card-img"
                  src="{{ post.thumbnail | relative_url }}"
                  style="object-fit: cover; height: 90%"
                  alt="{{ post.title }}"
                >
              </a>
            </div>
          </div>
        {% endif %}
      </li>
    {% endfor %}
  </ul>

  {% if page.pagination.enabled %}
    {% include pagination.liquid %}
  {% endif %}
</div>
