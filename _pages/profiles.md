---
layout: page
permalink: /people/
title: Member
description: members of the lab
nav: true
nav_order: 3
---

<style>
  :root {
    --global-theme-color: #2c4a6e;
    --global-hover-color: #3a6089;
    --global-divider-color: rgba(15, 23, 42, 0.08);
  }
  html[data-theme="dark"] {
    --global-theme-color: #86aed6;
    --global-hover-color: #a5c4e3;
    --global-divider-color: #33383f;
  }

  body {
    font-weight: 400;
  }

  .navbar .navbar-nav .nav-item {
    margin: 0 0.4rem;
  }
  .navbar .navbar-nav .nav-item .nav-link {
    font-size: 0.85rem;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    padding-bottom: 0.35rem;
    border-bottom: 2px solid transparent;
  }
  .navbar .navbar-nav .nav-item .nav-link:hover {
    border-bottom-color: var(--global-divider-color);
  }
  .navbar .navbar-nav .nav-item.active > .nav-link {
    border-bottom-color: var(--global-theme-color);
  }

  .post-header {
    display: none;
  }

  footer[role="contentinfo"] {
    display: none !important;
  }

  .people-pi {
    display: flex;
    gap: 2rem;
    align-items: flex-start;
    flex-wrap: wrap;
    margin-bottom: 2.5rem;
    padding-bottom: 2.5rem;
    border-bottom: 1px solid var(--global-divider-color);
  }
  .people-pi img,
  .people-card img {
    width: 100%;
    max-width: 180px;
    aspect-ratio: 1 / 1;
    object-fit: cover;
    border-radius: 50%;
  }
  .people-pi .people-info {
    flex: 1;
    min-width: 240px;
  }
  .people-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 1.5rem;
  }
  @media (max-width: 768px) {
    .people-grid {
      grid-template-columns: 1fr;
    }
  }
  .people-card {
    text-align: center;
    padding: 1.75rem 1.25rem;
    border: 1px solid var(--global-divider-color);
    border-radius: 14px;
    transition:
      border-color 0.2s ease,
      transform 0.2s ease;
  }
  .people-card:hover {
    border-color: var(--global-theme-color);
    transform: translateY(-2px);
  }
  .people-card img {
    max-width: 140px;
    margin: 0 auto;
  }
  .people-card .people-info {
    margin-top: 1rem;
  }
  .people-role {
    opacity: 0.65;
    font-size: 0.85rem;
    letter-spacing: 0.02em;
    margin-bottom: 0.5rem;
  }
  .people-links a {
    margin: 0 0.4rem;
  }
  .people-empty {
    text-align: center;
    opacity: 0.6;
    padding: 2rem 0;
  }
</style>

{% assign pi = site.data.people.pi %}

<div class="people-pi">
  {% if pi.photo %}
    {% assign pi_image_path = pi.photo | prepend: 'assets/img/' %}
    {% include figure.liquid loading="eager" path=pi_image_path class="img-fluid z-depth-1 rounded" alt=pi.name cache_bust=true %}
  {% endif %}
  <div class="people-info">
    <h2>{{ pi.name }}</h2>
    {% if pi.role %}<p class="people-role">{{ pi.role }}</p>{% endif %}
    {% if pi.bio %}<p>{{ pi.bio }}</p>{% endif %}
    {% if pi.email or pi.homepage or pi.linkedin or pi.scholar %}
      <p class="people-links">
        {% if pi.email %}<a href="mailto:{{ pi.email }}" title="Email"><i class="fa-solid fa-envelope"></i></a>{% endif %}
        {% if pi.homepage %}<a href="{{ pi.homepage }}" target="_blank" rel="noopener" title="Homepage"><i class="fa-solid fa-globe"></i></a>{% endif %}
        {% if pi.linkedin %}<a href="{{ pi.linkedin }}" target="_blank" rel="noopener" title="LinkedIn"><i class="fa-brands fa-linkedin"></i></a>{% endif %}
        {% if pi.scholar %}<a href="{{ pi.scholar }}" target="_blank" rel="noopener" title="Google Scholar"><i class="ai ai-google-scholar"></i></a>{% endif %}
      </p>
    {% endif %}
  </div>
</div>

<hr />

<h2>students</h2>

{% if site.data.people.students and site.data.people.students.size > 0 %}

  <div class="people-grid">
    {% for s in site.data.people.students %}
      <div class="people-card">
        {% if s.photo %}
          {% assign s_image_path = s.photo | prepend: 'assets/img/' %}
          {% include figure.liquid path=s_image_path class="img-fluid z-depth-1 rounded" alt=s.name cache_bust=true %}
        {% endif %}
        <div class="people-info">
          <h3>{{ s.name }}</h3>
          {% if s.role %}<p class="people-role">{{ s.role }}</p>{% endif %}
          {% if s.bio %}<p>{{ s.bio }}</p>{% endif %}
          {% if s.email or s.homepage or s.scholar %}
            <p class="people-links">
              {% if s.email %}<a href="mailto:{{ s.email }}" title="Email"><i class="fa-solid fa-envelope"></i></a>{% endif %}
              {% if s.homepage %}<a href="{{ s.homepage }}" target="_blank" rel="noopener" title="Homepage"><i class="fa-solid fa-globe"></i></a>{% endif %}
              {% if s.scholar %}<a href="{{ s.scholar }}" target="_blank" rel="noopener" title="Google Scholar"><i class="ai ai-google-scholar"></i></a>{% endif %}
            </p>
          {% endif %}
        </div>
      </div>
    {% endfor %}
  </div>
{% else %}
  <p class="people-empty">아직 합류한 학생이 없습니다. 곧 업데이트될 예정입니다.</p>
{% endif %}
