---
layout: default
title: Blog
permalink: /blog/
---

# Blog Categories

<div class="blog-categories">
  <div class="category-section">
    <h2><a href="/blog/programming/">Programming Blogs</a></h2>
    <p>Technical articles about programming, robotics code, and software development.</p>
    
    <div class="recent-posts">
      {% assign programming_posts = site.posts | where_exp: "post", "post.path contains '_programming'" %}
      {% for post in programming_posts limit:3 %}
        <div class="post-preview">
          <h3><a href="{{ post.url | relative_url }}">{{ post.title | escape }}</a></h3>
          <p class="post-meta">{{ post.date | date: "%b %-d, %Y" }}</p>
          {% if post.excerpt %}
            <p>{{ post.excerpt | strip_html | truncatewords:30 }}</p>
          {% endif %}
        </div>
      {% endfor %}
      {% if programming_posts.size == 0 %}
        <p><em>No programming posts yet. Check back soon!</em></p>
      {% endif %}
    </div>
  </div>

  <div class="category-section">
    <h2><a href="/blog/general/">General Updates</a></h2>
    <p>Team updates, competition results, and general robotics news.</p>
    
    <div class="recent-posts">
      {% assign general_posts = site.posts | where_exp: "post", "post.path contains '_general'" %}
      {% for post in general_posts limit:3 %}
        <div class="post-preview">
          <h3><a href="{{ post.url | relative_url }}">{{ post.title | escape }}</a></h3>
          <p class="post-meta">{{ post.date | date: "%b %-d, %Y" }}</p>
          {% if post.excerpt %}
            <p>{{ post.excerpt | strip_html | truncatewords:30 }}</p>
          {% endif %}
        </div>
      {% endfor %}
      {% if general_posts.size == 0 %}
        <p><em>No general posts yet. Check back soon!</em></p>
      {% endif %}
    </div>
  </div>
</div>

## All Recent Posts

<div class="all-posts">
  {% assign all_posts = site.posts | sort: 'date' | reverse %}
  {% for post in all_posts limit:10 %}
    <div class="post-preview">
      <h3><a href="{{ post.url | relative_url }}">{{ post.title | escape }}</a></h3>
      <p class="post-meta">{{ post.date | date: "%b %-d, %Y" }} • 
        {% if post.path contains '_programming' %}
          Category: Programming
        {% elsif post.path contains '_general' %}
          Category: General
        {% endif %}
      </p>
      {% if post.excerpt %}
        <p>{{ post.excerpt | strip_html | truncatewords:50 }}</p>
      {% endif %}
    </div>
  {% endfor %}
</div>
