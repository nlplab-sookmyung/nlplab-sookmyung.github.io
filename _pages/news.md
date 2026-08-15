---
layout: page
title: news
permalink: /news/
nav: true
nav_order: 1
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

  .news .table {
    width: 100%;
    border-collapse: collapse;
  }
  .news .table tr {
    display: flex;
    flex-wrap: wrap;
    gap: 0.25rem 1.5rem;
    padding: 0.9rem 0;
    border-bottom: 1px solid var(--global-divider-color);
  }
  .news .table tr:first-child {
    border-top: 1px solid var(--global-divider-color);
  }
  .news .table th,
  .news .table td {
    border: none;
    padding: 0;
  }
  .news .table th {
    flex: 0 0 auto;
    width: auto !important;
    font-weight: 600;
    font-size: 0.78rem;
    letter-spacing: 0.05em;
    text-transform: uppercase;
    color: var(--global-text-color-light);
    white-space: nowrap;
  }
  .news .table td {
    flex: 1 1 260px;
  }
</style>

{% include news.liquid %}
