---
title: Experiments
layout: default
permalink: /experiments/
---

# Experiments

{% for post in site.posts %}
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

<style>
  .post-card {
    background: var(--card-bg, #2d2d2d);
    border-radius: 8px;
    padding: 1.5em;
    margin-bottom: 1.5em;
    box-shadow: 0 2px 5px rgba(0,0,0,0.1);
  }
  
  .post-meta {
    color: #aaa;
    font-size: 0.9em;
    margin-bottom: 0.5em;
  }
  
  .tags {
    display: flex;
    flex-wrap: wrap;
    gap: 0.5em;
    margin-top: 1em;
  }
  
  .tag {
    background: #444;
    color: #ddd;
    padding: 2px 8px;
    border-radius: 4px;
    font-size: 0.8em;
  }
</style>