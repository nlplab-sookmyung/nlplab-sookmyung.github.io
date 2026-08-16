---
layout: about
title: about
permalink: /
subtitle: Sookmyung Women's University Natural Language Processing Lab

selected_papers: true # includes a list of papers marked as "selected={true}"
social: false # includes social icons at the bottom of the page

announcements:
  enabled: true # includes a list of news items
  scrollable: true # adds a vertical scroll bar if there are more than 3 news items
  limit: 5 # leave blank to include all the news in the `_news` folder
---

<style>
  :root {
    --global-theme-color: #2c4a6e;
    --global-hover-color: #3a6089;
    --global-divider-color: rgba(15, 23, 42, 0.08);
    --global-badge-color: #6a90bd;
    --global-badge-conference-color: #6a90bd;
    --global-badge-journal-color: #4f9e8b;
    --global-badge-arxiv-color: #c17a4a;
  }
  html[data-theme="dark"] {
    --global-theme-color: #86aed6;
    --global-hover-color: #a5c4e3;
    --global-divider-color: #33383f;
    --global-badge-color: #4a72a0;
    --global-badge-conference-color: #4a72a0;
    --global-badge-journal-color: #3c7d6d;
    --global-badge-arxiv-color: #a3623a;
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

  /* Hero band: full-bleed colored row behind the lab name */
  .post-header {
    background: var(--global-theme-color);
    box-shadow: 0 0 0 100vmax var(--global-theme-color);
    clip-path: inset(0 -100vmax);
    padding: 6rem 1.5rem 4.5rem;
    margin-bottom: 3rem;
    text-align: center;
  }
  .post-title {
    color: #fff;
    font-weight: 800;
    letter-spacing: -0.02em;
    font-size: clamp(2.75rem, 6vw, 4rem);
    line-height: 1.05;
  }
  .post-header .desc {
    font-size: 1.15rem;
    color: rgba(255, 255, 255, 0.88);
    margin-top: 0.5rem;
  }
  .post-header .desc::after {
    content: "숙명여대 자연어처리연구실";
    display: block;
    font-size: 0.85rem;
    color: rgba(255, 255, 255, 0.65);
    margin-top: 0.4rem;
  }

  footer[role="contentinfo"] {
    display: none !important;
  }

  /* Reflow article children (contact goes after news/publications without
     touching the gem-owned about.liquid layout): unwrap .clearfix into the
     article's flex context, then push .lab-contact to the end with `order`. */
  article {
    display: flex;
    flex-direction: column;
  }
  .clearfix {
    display: contents;
  }

  article > h2 {
    font-size: 1.4rem;
    font-weight: 700;
    letter-spacing: -0.01em;
    margin-top: 3rem;
    margin-bottom: 1rem;
  }
  article > h2 a[href$="/news/"],
  article > h2 a[href$="/publications/"] {
    font-size: 0;
    display: inline-flex;
    align-items: center;
    gap: 0.65rem;
    text-decoration: none;
  }
  article > h2 a[href$="/news/"]::before {
    content: "Recent News";
    font-size: 1.4rem;
    font-weight: 700;
  }
  article > h2 a[href$="/publications/"]::before {
    content: "Selected Publications";
    font-size: 1.4rem;
    font-weight: 700;
  }
  article > h2 a[href$="/news/"]::after,
  article > h2 a[href$="/publications/"]::after {
    content: "+";
    font-size: 1.1rem;
    font-weight: 600;
    width: 1.6rem;
    height: 1.6rem;
    line-height: 1;
    flex: none;
    display: inline-flex;
    align-items: center;
    justify-content: center;
    border: 1.5px solid var(--global-divider-color);
    border-radius: 50%;
    color: var(--global-theme-color);
    transition:
      background 0.15s ease,
      color 0.15s ease,
      border-color 0.15s ease;
  }
  article > h2 a[href$="/news/"]:hover::after,
  article > h2 a[href$="/publications/"]:hover::after {
    background: var(--global-theme-color);
    border-color: var(--global-theme-color);
    color: #fff;
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

  .publications {
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
    font-weight: 600;
  }
  .publications ol.bibliography li .abbr abbr {
    font-size: 0.68rem;
    font-weight: 600;
    letter-spacing: 0.01em;
    line-height: 1.25;
    border-radius: 6px;
    padding: 0.2rem 0.4rem;
    margin-bottom: 0;
    white-space: normal;
    text-align: center;
    background-color: var(--global-badge-color);
  }
  .publications ol.bibliography li .row {
    display: grid;
    grid-template-columns: minmax(115px, 12%) 1fr;
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
  }
  .publications ol.bibliography li .row > .col-sm-8 {
    display: contents;
  }
  .publications ol.bibliography li .title {
    grid-area: title;
  }
  .publications ol.bibliography li .author {
    grid-area: author;
    padding-left: 0.35rem;
  }
  .publications ol.bibliography li .author > em {
    border-bottom: none;
  }
  .publications ol.bibliography li .periodical {
    grid-area: period1;
    padding-left: 0.35rem;
    font-size: 0.98rem;
    font-weight: 600;
    color: var(--global-text-color-light);
  }
  .publications ol.bibliography li .periodical + .periodical {
    grid-area: period2;
  }
  .publications ol.bibliography li .links {
    grid-area: links;
    align-self: start;
  }

  .lab-contact {
    order: 10;
    margin-top: 3rem;
    padding-top: 1.5rem;
    border-top: 1px solid var(--global-divider-color);
  }
  .lab-contact h2 {
    font-size: 1.05rem;
    font-weight: 600;
    letter-spacing: 0.03em;
    opacity: 0.55;
    margin-bottom: 0.75rem;
  }
  .lab-contact a {
    font-weight: 600;
  }
</style>

<div class="intro-block" markdown="1">

SMU-NLP is the Natural Language Processing Lab at Sookmyung Women's University. We work outward from language understanding and generation into AI agents, evaluation, resource building, human-integrated AI, and turning research results into real applications.

Our goal is to find problems nobody has properly solved yet and push the frontier of NLP research forward. We build the core techniques behind understanding and generating language, design agents that plan and act on their own, and work out evaluation methods we can actually trust. We explore how people and AI can work side by side, and carry what we learn into real applications.

</div>

<div class="lab-contact" markdown="1">

## contact

연구실 참여, 협업 등 문의는 아래 이메일로 연락주시기 바랍니다.

[hyns.moon@sookmyung.ac.kr](mailto:hyns.moon@sookmyung.ac.kr)

</div>
