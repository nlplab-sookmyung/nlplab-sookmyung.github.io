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

  footer[role="contentinfo"] {
    display: none !important;
  }

  /* Bilingual intro blocks */
  .intro-lang-label {
    font-size: 0.72rem;
    font-weight: 700;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    opacity: 0.5;
    margin-bottom: 0.6rem;
  }
  .intro-block + .intro-divider {
    border: none;
    border-top: 1px solid var(--global-divider-color);
    margin: 2.25rem 0;
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
  }
  article > h2 a[href$="/news/"]::after {
    content: "Recent News";
    font-size: 1.4rem;
    font-weight: 700;
  }
  article > h2 a[href$="/publications/"]::after {
    content: "Selected Publications";
    font-size: 1.4rem;
    font-weight: 700;
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

<p class="intro-lang-label">한국어</p>

**SMU-NLP**(Sookmyung Women's University Natural Language Processing Lab)는 자연어처리(NLP)를 중심으로 AI, AI 에이전트, 평가(Evaluation), 리소스(Resource) 구축, 인간 참여형(Human-integrated) AI, 그리고 이를 실제 문제에 적용하는 응용 전략(Application Strategy)까지 폭넓게 연구합니다.

우리 연구실은 언어모델이 실제 환경에서 신뢰성 있게 동작하도록 만드는 데 관심이 있으며, 이를 위해 다음과 같은 주제들을 다룹니다:

- **Natural Language Processing**: 언어 이해 및 생성 관련 핵심 기술 연구
- **AI / AI Agent**: 자율적으로 계획하고 행동하는 에이전트 시스템 연구
- **Evaluation**: 모델과 시스템의 성능을 신뢰성 있게 평가하는 방법론 연구
- **Resource**: 연구와 응용에 필요한 데이터셋 및 벤치마크 구축
- **Human-integrated AI**: 사람과 AI가 함께 협업하는 시스템 연구
- **Application Strategy**: 연구 성과를 실제 문제에 적용하기 위한 전략 연구

Publications는 [Google Scholar](https://scholar.google.com/citations?user=queGQ5UAAAAJ&hl=ko) 프로필에서도 확인하실 수 있습니다.

</div>

<hr class="intro-divider" />

<div class="intro-block" markdown="1">

<p class="intro-lang-label">English</p>

**SMU-NLP** (Sookmyung Women's University Natural Language Processing Lab) conducts broad research centered on natural language processing (NLP), spanning AI, AI agents, evaluation, resource construction, human-integrated AI, and application strategies for real-world problems.

We are interested in making language models work reliably in real-world settings, and our work spans the following areas:

- **Natural Language Processing**: core technologies for language understanding and generation
- **AI / AI Agent**: autonomous agent systems that plan and act
- **Evaluation**: methodologies for reliably evaluating models and systems
- **Resource**: building datasets and benchmarks for research and applications
- **Human-integrated AI**: systems where humans and AI collaborate
- **Application Strategy**: strategies for applying research outcomes to real-world problems

Publications are also available on our [Google Scholar](https://scholar.google.com/citations?user=queGQ5UAAAAJ&hl=ko) profile.

</div>

<div class="lab-contact" markdown="1">

## contact

연구실 참여, 협업 문의는 아래 이메일로 연락해주세요.

[hyns.moon@sookmyung.ac.kr](mailto:hyns.moon@sookmyung.ac.kr)

</div>
