---
layout: default
title: Tianyang He | Homepage
description: Modern academic homepage for Tianyang He, focusing on machine learning, vision, and systems.
---

{% assign home = site.data.home %}

<section class="hero" id="top">
  <div class="hero-text">
    <p class="eyebrow">{{ home.hero.eyebrow }}</p>
    <h1>{{ home.hero.name }} <span>{{ home.hero.name_zh }}</span></h1>
    <p class="lead">{{ home.hero.intro }}</p>
    <div class="hero-actions">
      {% for action in home.hero.actions %}
        <a class="button{% if action.style == 'ghost' %} ghost{% endif %}" href="{{ action.href }}">{{ action.label }}</a>
      {% endfor %}
    </div>
    <div class="chips">
      {% for chip in home.hero.chips %}
        <span>{{ chip }}</span>
      {% endfor %}
    </div>
  </div>
  <div class="hero-portrait">
    <img src="{{ '/selfie.jpg' | relative_url }}" alt="Portrait of Tianyang He">
  </div>
</section>

<section class="section" id="about">
  <div class="section-header">
    <h2><span class="section-icon">{{ home.about.icon }}</span>{{ home.about.title }}</h2>
    <p>{{ home.about.subtitle }}</p>
  </div>
  <div class="about-grid">
    {% for item in home.about.items %}
      <div class="about-card">
        <h3><span class="card-icon">{{ item.icon }}</span>{{ item.title }}</h3>
        <p>{{ item.body }}</p>
      </div>
    {% endfor %}
  </div>
</section>

<section class="section" id="publications">
  <div class="section-header">
    <h2><span class="section-icon">{{ home.publications.icon }}</span>{{ home.publications.title }}</h2>
    <p>{{ home.publications.subtitle }}</p>
  </div>
  {% for pub in home.publications.items %}
    <article class="pub-card">
      <div class="pub-meta">{{ pub.venue }} | {{ pub.year }}</div>
      <h3>{{ pub.title }}</h3>
      <p>{{ pub.authors | replace: "Tianyang He", "<strong>Tianyang He</strong>" }}</p>
      <p>DOI: <a class="text-link" href="https://doi.org/{{ pub.doi }}">{{ pub.doi }}</a></p>
      <div class="pub-links">
        {% for link in pub.links %}
          <a href="{{ link.url }}">{{ link.label }}</a>
        {% endfor %}
      </div>
    </article>
  {% endfor %}
</section>

<section class="section" id="research">
  <div class="section-header">
    <h2><span class="section-icon">{{ home.research.icon }}</span>{{ home.research.title }}</h2>
    <p>{{ home.research.subtitle }}</p>
  </div>
  <div class="interest-grid">
    {% for area in home.research.items %}
      <div class="interest-card">
        <h3><span class="card-icon">{{ area.icon }}</span>{{ area.title }}</h3>
        <ul>
          {% for point in area.points %}
            <li>{{ point }}</li>
          {% endfor %}
        </ul>
      </div>
    {% endfor %}
  </div>
</section>
