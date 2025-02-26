---
layout: page
title: Gallery
description: A collection of my favorite images and figures.
permalink: /gallery/
nav: true
nav_order: 5
---

<div class="gallery">
  <figure>
    <img src="/assets/img/1.jpg" alt="Description of Image 1">
    <figcaption>Short description for Image 1.</figcaption>
  </figure>

  <figure>
    <img src="/assets/img/2.jpg" alt="Description of Image 2">
    <figcaption>Short description for Image 2.</figcaption>
  </figure>

  <figure>
    <img src="/assets/img/3.jpg" alt="Description of Image 3">
    <figcaption>Short description for Image 3.</figcaption>
  </figure>
</div>

<style>
  .gallery {
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
  }
  figure {
    flex: 1 1 calc(33.333% - 40px);
    margin: 0;
    text-align: center;
  }
  img {
    max-width: 100%;
    height: auto;
    border-radius: 8px;
  }
  figcaption {
    margin-top: 10px;
    font-style: italic;
    color: #666;
  }
</style>
