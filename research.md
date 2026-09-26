---
layout: page
permalink: /research/
title: Research
---

<div class="p-page research-overview">
  <header class="p-intro">
    <p class="p-label">Projects and research directions</p>
    <p>My research connects immune profiling, computational prediction, and network biology. Explore the questions, approaches, and publications behind each area.</p>
  </header>
  <div class="p-grid">
    {% for project in site.data.research_projects %}
    <article class="p-card" id="{{ project.ids.first }}">
      {% for project_id in project.ids offset:1 %}<span id="{{ project_id }}"></span>{% endfor %}
      <p class="p-label">{{ project.area }}</p>
      <h2><a href="{{ '/research/' | append: project.slug | append: '/' | relative_url }}">{{ project.title }}</a></h2>
      <p>{{ project.summary }}</p>
      <a href="{{ '/research/' | append: project.slug | append: '/' | relative_url }}" aria-label="Explore {{ project.title }}">Explore project →</a>
    </article>
    {% endfor %}
  </div>
  <section class="research-resources">
    <p class="p-label">Data and teaching</p>
    <h2>Resources from the research</h2>
    <p>Access CMI-PB data and prediction challenges, alongside teaching materials for systems vaccinology.</p>
    <a href="{{ '/resources/' | relative_url }}">Browse resources →</a>
  </section>
</div>
