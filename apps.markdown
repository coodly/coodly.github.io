---
layout: default
title: Apps
---

# Our Apps

<div class="apps-grid">
{% for app in site.data.apps %}
<div class="app-card">
  <div class="app-icon">{{ app.icon }}</div>
  <div class="app-info">
    <h3>{{ app.name }}</h3>
    <p>{{ app.description }}</p>
    <a href="{{ app.app_store_url }}">View on App Store →</a>
  </div>
</div>
{% endfor %}
</div>

<style>
.apps-grid {
  display: grid;
  gap: 2rem;
  margin-top: 2rem;
}

.app-card {
  display: flex;
  align-items: center;
  gap: 1rem;
  padding: 1.5rem;
  border: 1px solid #e9ecef;
  border-radius: 8px;
}

.app-icon {
  width: 80px;
  height: 80px;
  background: #f8f9fa;
  border-radius: 16px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 2rem;
  flex-shrink: 0;
}

.app-info {
  flex: 1;
}

.app-info h3 {
  margin: 0 0 0.5rem 0;
}

.app-info p {
  margin: 0 0 1rem 0;
  color: #666;
}

.app-info a {
  color: #007aff;
  text-decoration: none;
}
</style>