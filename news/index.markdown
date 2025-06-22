---
layout: default
title: News
---

# News & Updates

<div class="posts">
  {% for post in site.posts %}
    <article class="post">
      <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
      <time class="post-date">{{ post.date | date: "%B %d, %Y" }}</time>
      <p>{{ post.excerpt | strip_html | truncatewords: 30 }}</p>
      <a href="{{ post.url }}" class="read-more">Read more →</a>
    </article>
  {% endfor %}
</div>

<style>
.posts {
  margin-top: 2rem;
}

.post {
  margin-bottom: 3rem;
  padding-bottom: 2rem;
  border-bottom: 1px solid #e9ecef;
}

.post:last-child {
  border-bottom: none;
}

.post h2 {
  margin: 0 0 0.5rem 0;
  font-size: 1.5rem;
}

.post h2 a {
  color: #159957;
  text-decoration: none;
}

.post h2 a:hover {
  text-decoration: underline;
}

.post-date {
  color: #666;
  font-size: 0.9rem;
}

.post p {
  margin: 1rem 0;
  line-height: 1.6;
}

.read-more {
  color: #007aff;
  text-decoration: none;
  font-weight: 500;
}

.read-more:hover {
  text-decoration: underline;
}

.pagination {
  margin-top: 3rem;
  text-align: center;
}

.pagination-item {
  display: inline-block;
  padding: 0.5rem 1rem;
  margin: 0 0.25rem;
  color: #007aff;
  text-decoration: none;
  border: 1px solid #e9ecef;
  border-radius: 4px;
}

.pagination-item:hover {
  background: #f8f9fa;
}

.pagination-item:not([href]) {
  color: #ccc;
  cursor: not-allowed;
}
</style>