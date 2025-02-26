---
layout: page
title: Awards
description: A list of awards and recognitions I have received.
permalink: /awards/
nav: true
nav_order: 7
---

<div class="awards">
  {% for award in site.awards %}
    <div class="award">
      <h3 class="award-title">{{ award.title }}</h3>
      <div class="award-details">
        <span class="award-organization">{{ award.organization }}</span> &middot;
        <span class="award-date">{{ award.date | date: "%B %Y" }}</span>
      </div>
      {% if award.description %}
        <div class="award-description">
          {{ award.description | markdownify }}
        </div>
      {% endif %}
    </div>
    <hr>
  {% endfor %}
</div>
