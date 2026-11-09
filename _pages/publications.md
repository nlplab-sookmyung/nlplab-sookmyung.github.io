---
layout: page
permalink: /publications/
title: Publications
nav: true
nav_order: 2
---

<!-- _pages/publications.md -->

<style>
  @font-face {
    font-family: "SUIT";
    src: url("{{ '/assets/fonts/SUIT-ttf/SUIT-Regular.woff2' | relative_url }}") format("woff2");
    font-weight: 400;
    font-style: normal;
    font-display: swap;
  }
  @font-face {
    font-family: "SUIT";
    src: url("{{ '/assets/fonts/SUIT-ttf/SUIT-Medium.woff2' | relative_url }}") format("woff2");
    font-weight: 500;
    font-style: normal;
    font-display: swap;
  }
  @font-face {
    font-family: "SUIT";
    src: url("{{ '/assets/fonts/SUIT-ttf/SUIT-SemiBold.woff2' | relative_url }}") format("woff2");
    font-weight: 600;
    font-style: normal;
    font-display: swap;
  }
  @font-face {
    font-family: "SUIT";
    src: url("{{ '/assets/fonts/SUIT-ttf/SUIT-Bold.woff2' | relative_url }}") format("woff2");
    font-weight: 700;
    font-style: normal;
    font-display: swap;
  }
  @font-face {
    font-family: "SUIT";
    src: url("{{ '/assets/fonts/SUIT-ttf/SUIT-ExtraBold.woff2' | relative_url }}") format("woff2");
    font-weight: 800;
    font-style: normal;
    font-display: swap;
  }
  @font-face {
    font-family: "SUIT";
    src: url("{{ '/assets/fonts/SUIT-ttf/SUIT-Heavy.woff2' | relative_url }}") format("woff2");
    font-weight: 900;
    font-style: normal;
    font-display: swap;
  }

  :root {
    --global-theme-color: #2c4a6e;
    --global-hover-color: #3a6089;
    --global-divider-color: rgba(15, 23, 42, 0.08);
    --global-badge-color: #6a90bd;
    --global-badge-conference-color: #6a90bd;
    --global-badge-journal-color: #4f9e8b;
    --global-badge-arxiv-color: #c17a4a;
    --global-periodical-color: #555d69;
  }
  html[data-theme="dark"] {
    --global-theme-color: #86aed6;
    --global-hover-color: #a5c4e3;
    --global-divider-color: #33383f;
    --global-badge-color: #4a72a0;
    --global-badge-conference-color: #4a72a0;
    --global-badge-journal-color: #3c7d6d;
    --global-badge-arxiv-color: #a3623a;
    --global-periodical-color: #b4bac3;
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

  .publications {
    font-family: "SUIT", "Roboto", sans-serif;
    font-size: 0.92rem;
  }
  div.publications h2.bibliography {
    display: block;
    box-sizing: border-box;
    width: 100%;
    font-size: 1rem;
    font-weight: 700;
    letter-spacing: 0.05em;
    color: #fff;
    opacity: 1;
    text-align: right;
    background: var(--global-theme-color);
    border-radius: 6px;
    padding: 0.55rem 1rem;
    margin-top: 2.5rem;
    margin-bottom: 1.25rem;
    border-top: none;
  }
  div.publications h2.bibliography:first-of-type {
    margin-top: 0;
  }
  .publications ol.bibliography li {
    padding-bottom: 0.85rem;
    margin-bottom: 0.85rem;
  }
  .publications ol.bibliography li:last-child {
    padding-bottom: 0;
    margin-bottom: 0;
  }
  .publications ol.bibliography li .title {
    font-size: 1rem;
    font-weight: 700;
  }
  .publications ol.bibliography li .abbr abbr {
    font-family: "SUIT", "Roboto", sans-serif;
    font-size: 0.9rem;
    font-weight: 900;
    letter-spacing: 0.01em;
    line-height: 1.25;
    border-radius: 6px;
    padding: 0.3rem 0.45rem;
    margin-bottom: 0;
    white-space: normal;
    text-align: center;
    background-color: var(--global-badge-color);
  }
  /* white text for every venue badge; the gem sets abbr color with !important,
     and venues registered in _data/venues.yml wrap the label in a <div> */
  .publications ol.bibliography li .abbr abbr,
  .publications ol.bibliography li .abbr abbr div,
  .publications ol.bibliography li .abbr abbr a {
    color: #fff !important;
  }
  .publications ol.bibliography li .row {
    display: grid;
    grid-template-columns: minmax(150px, 13%) 1fr;
    column-gap: 1.5rem;
    row-gap: 0.15rem;
    align-items: start;
    margin-left: 0;
    margin-right: 0;
    grid-template-areas:
      "abbr title"
      "links author"
      "links period1"
      "links period2";
  }
  .publications ol.bibliography li .row > .col-sm-2.abbr {
    grid-area: abbr;
    width: auto;
    max-width: none;
    flex: none;
    padding: 0;
    margin-bottom: 0;
    /* match the title line height so the taller badge does not stretch
       the first grid row and push the author list down */
    height: 1.35rem;
    overflow: visible;
  }
  .publications ol.bibliography li .row > .col-sm-8 {
    display: contents;
  }
  .publications ol.bibliography li .title {
    grid-area: title;
    line-height: 1.35;
  }
  .publications ol.bibliography li .author {
    grid-area: author;
    margin-top: -0.15rem;
  }
  .publications ol.bibliography li .author > em {
    border-bottom: none;
  }
  .publications ol.bibliography li .periodical {
    grid-area: period1;
    font-size: 0.9rem;
    font-weight: 400;
    color: var(--global-periodical-color);
  }
  .publications ol.bibliography li .periodical em {
    color: var(--global-periodical-color);
    font-style: normal;
  }
  .publications ol.bibliography li .periodical + .periodical {
    grid-area: period2;
  }
  .publications ol.bibliography li .links {
    grid-area: links;
    align-self: start;
    padding-top: 0.4rem;
  }
</style>

<div class="publications">

{% bibliography %}

</div>
