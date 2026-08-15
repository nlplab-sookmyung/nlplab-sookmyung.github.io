---
layout: page
permalink: /people/
title: people
description: members of the lab
nav: true
nav_order: 3
---

<style>
  footer[role="contentinfo"] {
    display: none !important;
  }
  .people-pi {
    display: flex;
    gap: 2rem;
    align-items: flex-start;
    flex-wrap: wrap;
    margin-bottom: 2.5rem;
  }
  .people-pi img,
  .people-card img {
    width: 100%;
    max-width: 220px;
    border-radius: 8px;
  }
  .people-pi .people-info {
    flex: 1;
    min-width: 240px;
  }
  .people-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 2rem;
  }
  @media (max-width: 768px) {
    .people-grid {
      grid-template-columns: 1fr;
    }
  }
  .people-card {
    text-align: center;
  }
  .people-card .people-info {
    margin-top: 0.75rem;
  }
  .people-role {
    opacity: 0.7;
    font-size: 0.9rem;
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
    {% if pi.email or pi.homepage or pi.scholar %}
      <p class="people-links">
        {% if pi.email %}<a href="mailto:{{ pi.email }}" title="Email"><i class="fa-solid fa-envelope"></i></a>{% endif %}
        {% if pi.homepage %}<a href="{{ pi.homepage }}" target="_blank" rel="noopener" title="Homepage"><i class="fa-solid fa-globe"></i></a>{% endif %}
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
