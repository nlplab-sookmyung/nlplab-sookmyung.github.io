---
layout: page
permalink: /publications/
title: Publications
nav: true
nav_order: 2
---

<!-- _pages/publications.md -->

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

  .post-title {
    font-weight: 700;
    letter-spacing: -0.01em;
  }
  .post-header .desc {
    font-size: 1.05rem;
    color: var(--global-text-color-light);
    margin-top: 0.25rem;
  }

  footer[role="contentinfo"] {
    display: none !important;
  }

  .publications {
    font-size: 0.92rem;
  }
  .publications h2 {
    font-size: 1.05rem;
    font-weight: 600;
    letter-spacing: 0.03em;
    opacity: 0.55;
    margin-top: 2.25rem;
  }
  .publications ol.bibliography li {
    padding-bottom: 1rem;
    margin-bottom: 1rem;
    border-bottom: 1px solid var(--global-divider-color);
  }
  .publications ol.bibliography li:last-child {
    border-bottom: none;
  }
  .publications ol.bibliography li .title {
    font-size: 1rem;
    font-weight: 600;
  }
  .publications ol.bibliography li .abbr abbr {
    font-size: 0.72rem;
    font-weight: 600;
    letter-spacing: 0.02em;
    border-radius: 999px;
    padding: 0.15rem 0.65rem;
  }
</style>

<!-- Bibsearch Feature -->

{% include bib_search.liquid %}

<div class="publications">

{% bibliography %}

</div>
