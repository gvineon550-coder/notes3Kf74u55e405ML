---
layout: page
title: Мои фото
permalink: /
---

<div class="photo-grid">
{% for file in site.static_files %}
  {% if file.path contains '/assets/images/' %}
    {% unless file.name contains '.gitkeep' %}
      <a href="{{ site.baseurl }}{{ file.path }}" target="_blank">
        <img src="{{ site.baseurl }}{{ file.path }}" alt="" loading="lazy">
      </a>
    {% endunless %}
  {% endif %}
{% endfor %}
</div>

<style>
.photo-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(180px, 1fr));
  gap: 10px;
  margin-top: 24px;
}
.photo-grid img {
  width: 100%;
  height: 180px;
  object-fit: cover;
  border-radius: 8px;
  transition: transform 0.2s, box-shadow 0.2s;
}
.photo-grid img:hover {
  transform: scale(1.03);
  box-shadow: 0 6px 16px rgba(0,0,0,0.15);
}
</style>
