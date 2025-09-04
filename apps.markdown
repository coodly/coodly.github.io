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
    {% if app.local_page %}
      <h3><a href="{{ app.local_page }}">{{ app.name }}</a></h3>
    {% else %}
      <h3>{{ app.name }}</h3>
    {% endif %}
    <p>{{ app.description }}</p>
    {% if app.coming_soon %}
      <button class="coming-soon-badge" onclick="openSignupModal('{{ app.name }}', '{{ app.google_form_id }}')">Coming Soon - Get Notified</button>
    {% else %}
      <a href="{{ app.app_store_url }}">
        <img src="https://tools.applemediaservices.com/api/badges/download-on-the-app-store/black/en-us?size=250x83" alt="Download on the App Store" style="height: 40px;">
      </a>
    {% endif %}
  </div>
</div>
{% endfor %}
</div>

<!-- Email Signup Modal -->
<div id="signupModal" class="modal">
  <div class="modal-content">
    <span class="close" onclick="closeSignupModal()">&times;</span>
    <h2 id="modalTitle">Get Notified</h2>
    <p>Enter your email to be notified when this app launches:</p>
    
    <iframe id="googleForm" src="" width="100%" height="400" frameborder="0" marginheight="0" marginwidth="0">
      Loading…
    </iframe>
  </div>
</div>

<script>
function openSignupModal(appName, formId) {
  document.getElementById('modalTitle').textContent = 'Get Notified - ' + appName;
  document.getElementById('googleForm').src = 'https://docs.google.com/forms/d/e/' + formId + '/viewform?embedded=true';
  document.getElementById('signupModal').style.display = 'block';
}

function closeSignupModal() {
  document.getElementById('signupModal').style.display = 'none';
  document.getElementById('googleForm').src = ''; // Clear form when closing
}

// Close modal when clicking outside
window.onclick = function(event) {
  const modal = document.getElementById('signupModal');
  if (event.target == modal) {
    closeSignupModal();
  }
}
</script>

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
  background: #007aff;
  color: white;
  border: none;
  border-radius: 6px;
  font-size: 14px;
  font-weight: 500;
  cursor: pointer;
  transition: background-color 0.2s;
}

.coming-soon-badge:hover {
  background: #0056b3;
}

.modal {
  display: none;
  position: fixed;
  z-index: 1000;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0,0,0,0.5);
}

.modal-content {
  background-color: white;
  margin: 15% auto;
  padding: 20px;
  border-radius: 8px;
  width: 90%;
  max-width: 500px;
  position: relative;
}

.close {
  color: #aaa;
  float: right;
  font-size: 28px;
  font-weight: bold;
  cursor: pointer;
}

.close:hover {
  color: black;
}
</style>