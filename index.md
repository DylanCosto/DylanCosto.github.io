---
title: Home
layout: default
permalink: /
---

# Welcome to MolWiz

Real data, real experiments—so you don't have to guess.  
Explore our FAQs, deep‑dives, and lab hacks below.

## Recent Experiments

<div class="post-grid">
  {% for post in site.posts limit:6 %}
    <div class="post-card">
      <h3><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
      <div class="post-meta">{{ post.date | date: "%B %-d, %Y" }}</div>
      <p>{{ post.description | default: post.excerpt | strip_html | truncate: 120 }}</p>
      <div class="tags">
        {% for tag in post.tags %}
          <span class="tag">{{ tag }}</span>
        {% endfor %}
      </div>
    </div>
  {% endfor %}
</div>

<style>
  .post-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
    gap: 1.5em;
    margin-top: 2em;
  }
  
  @media (max-width: 768px) {
    .post-grid {
      grid-template-columns: 1fr;
    }
  }
</style>