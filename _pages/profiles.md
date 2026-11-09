---
layout: page
permalink: /people/
title: Member
description: members of the lab
nav: true
nav_order: 1
---

<style>
  @font-face {
    font-family: "Bithumb Gothic";
    src: url("{{ '/assets/fonts/Bithumb/BithumbGothic-Basic.woff2' | relative_url }}") format("woff2");
    font-weight: 700;
    font-style: normal;
    font-display: swap;
  }
  @font-face {
    font-family: "Bookk Gothic";
    src: url("{{ '/assets/fonts/BookkGothic/BookkGothic_Light.woff2' | relative_url }}") format("woff2");
    font-weight: 300;
    font-style: normal;
    font-display: swap;
  }
  @font-face {
    font-family: "Bookk Gothic";
    src: url("{{ '/assets/fonts/BookkGothic/BookkGothic_Bold.woff2' | relative_url }}") format("woff2");
    font-weight: 700;
    font-style: normal;
    font-display: swap;
  }

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

  .navbar-brand.title {
    font-size: 0;
    display: inline-flex;
    align-items: center;
  }
  .navbar-brand.title::before {
    content: "";
    display: inline-block;
    width: 210px;
    height: 46px;
    background-image: url("{{ '/assets/img/icon/smu_nlp_combined_snowflake.svg' | relative_url }}");
    background-size: contain;
    background-repeat: no-repeat;
    background-position: left center;
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
    margin-bottom: 3rem;
    padding-bottom: 2.5rem;
    border-bottom: 1px solid var(--global-divider-color);
  }
  .people-pi img {
    width: 100%;
    max-width: 260px;
    aspect-ratio: 3 / 4;
    object-fit: cover;
    border-radius: 20px;
  }
  .people-card img {
    width: 100%;
    max-width: 180px;
    aspect-ratio: 1 / 1;
    object-fit: cover;
    border-radius: 50%;
  }
  /* name, role, address and bio of the professor and students */
  .people-info,
  .people-info h2,
  .people-info h3 {
    font-family: "Bookk Gothic", "Roboto", sans-serif;
  }
  .people-pi .people-info {
    flex: 1;
    min-width: 240px;
  }
  .people-grid {
    display: grid;
    grid-template-columns: repeat(3, minmax(0, 1fr));
    gap: 1.5rem;
    margin-bottom: 2.5rem;
  }
  @media (max-width: 768px) {
    .people-grid {
      grid-template-columns: repeat(2, minmax(0, 1fr));
    }
  }
  @media (max-width: 480px) {
    .people-grid {
      grid-template-columns: 1fr;
    }
  }
  .people-group-title {
    font-family: "Bithumb Gothic", "Roboto", sans-serif;
    font-weight: 700;
    font-size: 1.6rem;
    letter-spacing: 0;
    margin: 0 0 1.75rem;
  }
  .people-card {
    text-align: center;
    padding: 1.5rem 1rem;
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
    max-width: 200px;
    margin: 0 auto;
  }
  .people-card .people-info {
    margin-top: 1rem;
  }
  .people-card h3 {
    font-size: 1.2rem;
    margin-bottom: 0.25rem;
  }
  .people-info .people-title {
    font-family: "Bithumb Gothic", "Roboto", sans-serif;
    font-size: 1.4rem;
    font-weight: 700;
    letter-spacing: -0.01em;
    margin-bottom: 0.35rem;
  }
  .people-role {
    opacity: 0.65;
    font-size: 0.85rem;
    letter-spacing: 0.02em;
    margin-bottom: 0.5rem;
    line-height: 1.5;
  }
  .people-address {
    opacity: 0.55;
    font-size: 0.82rem;
    margin-bottom: 0.75rem;
  }
  .people-bio {
    opacity: 0.55;
    font-size: 0.78rem;
    line-height: 1.6;
    margin-bottom: 0.75rem;
  }
  .people-links a {
    margin: 0 0.4rem;
    font-size: 1.4rem;
  }
</style>

{% assign pi = site.data.people.pi %}

<div class="people-pi">
  {% if pi.photo %}
    {% assign pi_image_path = pi.photo | prepend: 'assets/img/' %}
    {% include figure.liquid loading="eager" path=pi_image_path class="img-fluid z-depth-1 rounded" alt=pi.name cache_bust=true %}
  {% endif %}
  <div class="people-info">
    {% if pi.title %}<p class="people-title">{{ pi.title }}</p>{% endif %}
    <h2>{{ pi.name }}</h2>
    {% if pi.role %}<p class="people-role">{{ pi.role }}</p>{% endif %}
    {% if pi.address %}<p class="people-address">{{ pi.address }}</p>{% endif %}
    {% if pi.bio %}<p class="people-bio">{{ pi.bio }}</p>{% endif %}
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

{% for group in site.data.people.student_groups %}
  {% if group.members and group.members.size > 0 %}
  <h2 class="people-group-title">{{ group.title }}</h2>
  <div class="people-grid">
    {% for s in group.members %}
      <div class="people-card">
        {% if s.photo %}
          {% assign s_image_path = s.photo | prepend: 'assets/img/' %}
          {% include figure.liquid path=s_image_path class="img-fluid z-depth-1 rounded" alt=s.name cache_bust=true %}
        {% endif %}
        <div class="people-info">
          <h3>{{ s.name }}</h3>
          {% if s.role %}<p class="people-role">{{ s.role }}</p>{% endif %}
          {% if s.bio %}<p class="people-bio">{{ s.bio }}</p>{% endif %}
          {% if s.email or s.homepage or s.github or s.scholar %}
            <p class="people-links">
              {% if s.email %}<a href="mailto:{{ s.email }}" title="Email"><i class="fa-solid fa-envelope"></i></a>{% endif %}
              {% if s.homepage %}<a href="{{ s.homepage }}" target="_blank" rel="noopener" title="Homepage"><i class="fa-solid fa-globe"></i></a>{% endif %}
              {% if s.github %}<a href="{{ s.github }}" target="_blank" rel="noopener" title="GitHub"><i class="fa-brands fa-github"></i></a>{% endif %}
              {% if s.scholar %}<a href="{{ s.scholar }}" target="_blank" rel="noopener" title="Google Scholar"><i class="ai ai-google-scholar"></i></a>{% endif %}
            </p>
          {% endif %}
        </div>
      </div>
    {% endfor %}
  </div>
  {% endif %}
{% endfor %}
