---
layout: page
permalink: /repositories/
title: Repositories
description: Open-source software I contribute to for molecular simulation and machine-learned interaction models.
nav: true
nav_order: 4
---

{% assign profile = site.data.repositories.github_profile %}

<div class="repo-page">
  {% if profile %}
  <div class="repo-profile">
    <div class="repo-profile-main">
      <div class="repo-profile-icon"><i class="fa-brands fa-github"></i></div>
      <div>
        <a class="repo-profile-name" href="{{ profile.url }}" target="_blank" rel="noopener noreferrer">{{ profile.name }}</a>
        <div class="repo-profile-handle">@{{ profile.username }}</div>
        {% if profile.bio %}
          <p class="repo-profile-bio">{{ profile.bio }}</p>
        {% endif %}
      </div>
    </div>
    <a class="repo-profile-link" href="{{ profile.url }}" target="_blank" rel="noopener noreferrer">View GitHub profile <i class="fa-solid fa-arrow-up-right-from-square"></i></a>
  </div>
  {% endif %}

  <h3 class="repo-section-title">Selected repositories</h3>

  <div class="repo-grid">
    {% for repo in site.data.repositories.github_repos %}
      <a class="repo-card" href="{{ repo.url }}" target="_blank" rel="noopener noreferrer">
        <div class="repo-card-top">
          <span class="repo-card-name"><i class="fa-solid fa-book-bookmark"></i> {{ repo.name }}</span>
          {% if repo.role %}<span class="repo-card-role">{{ repo.role }}</span>{% endif %}
        </div>
        <div class="repo-card-full">{{ repo.full_name }}</div>
        {% if repo.description %}
          <p class="repo-card-desc">{{ repo.description }}</p>
        {% endif %}
        <div class="repo-card-meta">
          {% if repo.language %}<span><span class="repo-lang-dot"></span>{{ repo.language }}</span>{% endif %}
          <span class="repo-card-cta">Open on GitHub <i class="fa-solid fa-arrow-right"></i></span>
        </div>
      </a>
    {% endfor %}
  </div>
</div>
