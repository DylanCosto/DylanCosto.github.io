---
title: Home
layout: default
permalink: /
---

<h1 style="color: var(--accent-color);">Welcome to MolFAQ</h1>

<h1 style="color: var(--accent-color);">MolFAQ</h1> is a hands-on resource for real-world molecular biology experiments. We test common questions that others wouldn't dare do in front of their PI's or lab supervisors.

Note: All of the experiments are to be taken with a grain of salt and are not representative of every lab, they are tailored for curious individuals. 

Note2: We will be stretching manufacture recommendations not to "debunk" their recommendations, but rather find cost or time saving alternatives. This does not mean the manufacture is negligent as they validate their protocols with commonality, such as storing reagents in a -20c freezer, when they could be stable at RT or 4c. 


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