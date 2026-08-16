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

  .post-header {
    display: none;
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
    font-size: 0.68rem;
    font-weight: 600;
    letter-spacing: 0.01em;
    line-height: 1.25;
    border-radius: 6px;
    padding: 0.3rem 0.4rem;
    white-space: normal;
    text-align: center;
  }
  .publications ol.bibliography li .row {
    display: grid;
    grid-template-columns: minmax(100px, 16%) 1fr;
    column-gap: 1.5rem;
    row-gap: 0.35rem;
    align-items: start;
    grid-template-areas:
      "abbr title"
      "links author"
      "links period1"
      "links period2";
  }
  .publications ol.bibliography li .row > .col-sm-2.abbr {
    grid-area: abbr;
  }
  .publications ol.bibliography li .row > .col-sm-8 {
    display: contents;
  }
  .publications ol.bibliography li .title {
    grid-area: title;
  }
  .publications ol.bibliography li .author {
    grid-area: author;
  }
  .publications ol.bibliography li .author > em {
    border-bottom: none;
  }
  .publications ol.bibliography li .periodical {
    grid-area: period1;
    font-weight: 600;
    color: var(--global-text-color);
  }
  .publications ol.bibliography li .periodical + .periodical {
    grid-area: period2;
  }
  .publications ol.bibliography li .links {
    grid-area: links;
    align-self: start;
  }
</style>

<div class="publications">

{% bibliography %}

</div>
