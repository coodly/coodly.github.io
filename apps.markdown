---
layout: default
title: Apps
---

# Our Apps

<div class="apps-grid">
{% for app in site.data.apps %}
<div class="app-card">
  <div class="app-icon">
    <img src="{{ app.icon }}" alt="{{ app.name }} icon">
  </div>
  <div class="app-info">
    <h3>{{ app.name }}</h3>
    <p>{{ app.description }}</p>
    {% if app.coming_soon %}
      <span class="coming-soon-badge">Coming Soon</span>
    {% else %}
      <a href="{{ app.app_store_url }}">
        <img src="https://tools.applemediaservices.com/api/badges/download-on-the-app-store/black/en-us?size=250x83" alt="Download on the App Store" style="height: 40px;">
      </a>
    {% endif %}
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
  border-radius: 16px;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-shrink: 0;
  overflow: hidden;
}

.app-icon img {
  width: 100%;
  height: 100%;
  object-fit: cover;
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

.coming-soon-badge {
  display: inline-block;
  padding: 8px 16px;
  background: #f0f0f0;
  color: #666;
  border-radius: 6px;
  font-size: 14px;
  font-weight: 500;
}
</style>