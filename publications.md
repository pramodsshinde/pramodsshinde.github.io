---
layout: page
permalink: /publications/
title: Publications
---

<div class="p-page">
  <header class="p-intro">
    <p>Publications and preprints, listed by year.</p>
    <a href="https://scholar.google.com/citations?user=2GeAO4IAAAAJ&amp;hl=en">Google Scholar profile →</a>
  </header>
  {% assign publication_years = site.data.publications | group_by: "year" | sort: "name" | reverse %}
  {% for year in publication_years %}
  <section class="p-area" aria-labelledby="year-{{ year.name }}">
    <header><h2 id="year-{{ year.name }}">{{ year.name }}</h2></header>
    <ul class="p-papers">
      {% for pub in year.items %}
      <li>
        {% if pub.url %}
        <a href="{{ pub.url | escape }}">{{ pub.title | escape }}</a>
        {% elsif pub.doi and pub.doi != 'N/A' %}
        <a href="https://doi.org/{{ pub.doi | escape }}">{{ pub.title | escape }}</a>
        {% else %}
        <strong>{{ pub.title | escape }}</strong>
        {% endif %}
        <span>{{ pub.author | escape }}</span>
        <span><em>{{ pub.journal | escape }}</em> · {{ pub.year }}</span>
      </li>
      {% endfor %}
    </ul>
  </section>
  {% endfor %}
</div>
