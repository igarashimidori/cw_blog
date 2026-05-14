---
permalink: /
title: "Blog"
excerpt: "All blog posts"
author_profile: true
---

<span class='anchor' id='blog-list'></span>

{% if site.posts and site.posts.size > 0 %}
{% assign sorted_posts = site.posts | sort: 'date' | reverse %}
{% assign grouped_posts = sorted_posts | group_by_exp: "post", "post.category | default: 'Uncategorized'" %}

<header class="blog-archive-header">
  <div>
    <h1>📝 All Posts</h1>
    <p>Notes, learning logs ......</p>
  </div>
  <span>{{ site.posts | size }} posts</span>
</header>

{% for group in grouped_posts %}
<section class="blog-category-section">
  <div class="blog-category-heading">
    <h2>{{ group.name }}</h2>
    <span>{{ group.items | size }} posts</span>
  </div>

  <div class="blog-grid">
  {% for post in group.items %}
    <a href="{{ post.url | relative_url }}" class="blog-card-link">
      <div class="blog-card">
        <div class="blog-card-image">
          <div class="blog-badge">{{ post.date | date: "%B, %Y" }}</div>
          {% if post.cover_image %}
          <img src="{{ post.cover_image | relative_url }}" alt="{{ post.title }}">
          {% else %}
          <img src="{{ '/images/500x300.png' | relative_url }}" alt="{{ post.title }}">
          {% endif %}
        </div>
        <div class="blog-card-content">
          <div class="blog-title">{{ post.title }}</div>
          <div class="blog-description">{{ post.description | default: post.excerpt | strip_html | truncate: 150 }}</div>
        </div>
      </div>
    </a>
  {% endfor %}
  </div>
</section>
{% endfor %}
{% else %}
<div class="quote-accent">
  <p>No blog posts yet. Check back soon!</p>
</div>
{% endif %}

