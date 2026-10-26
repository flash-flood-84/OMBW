---
layout: default
title: Mothman Brunch
---

<p class="eyebrow">A STORY</p>

<h1 class="home-title">Mothman Brunch</h1>

<p class="intro">
  Cryptid Hallmark movie.
</p>

<section class="story-section">
  <h2>Contents</h2>

  {% assign chapters = site.pages
    | where_exp: "page", "page.path contains 'stories/mothman_brunch/chapter-'"
    | sort: "path" %}

  {% for chapter in chapters %}
    <article class="story-entry">
      <h3>
        <a href="{{ chapter.url | relative_url }}">
          {{ chapter.title | default: chapter.name }}
        </a>
      </h3>

      <a class="read-link" href="{{ chapter.url | relative_url }}">
        {% if forloop.first %}
          Begin reading →
        {% else %}
          Read chapter →
        {% endif %}
      </a>
    </article>
  {% endfor %}
</section>