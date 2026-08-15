---
permalink: /
title: ""
layout: single
author_profile: false
classes: wide profile-page
---

{% assign site_profile = site.data.site_profile %}
{% include site-profile-styles.html %}

<div class="profile-shell">
  <header class="profile-hero">
    <p class="profile-eyebrow">Marketing · AI · Consumer Behaviour</p>
    <h1>{{ site_profile.profile.name }}</h1>
    <p class="profile-role">{{ site_profile.profile.role }} · {{ site_profile.profile.location }}</p>
    <ul class="profile-links">
      <li><a href="{{ site_profile.profile.scholar }}">Google Scholar</a></li>
      <li><a href="{{ site_profile.profile.orcid }}">ORCID</a></li>
      <li><a href="{{ site_profile.profile.linkedin }}">LinkedIn</a></li>
      <li><a href="{{ site_profile.profile.github }}">GitHub</a></li>
      <li><a class="profile-button--primary" href="{{ site.baseurl }}/files/Xiaotian_Liu_CV.pdf">Download CV</a></li>
    </ul>
  </header>

  <section class="profile-section">
    <h2><span>01</span>Research profile</h2>
    <p class="profile-lead">{{ site_profile.profile.research_statement }}</p>
    <p class="profile-meta"><strong>Methods:</strong> {{ site_profile.profile.methods }}<br><strong>Doctoral status:</strong> {{ site_profile.profile.doctoral_status }}</p>
  </section>

  <section class="profile-section">
    <h2><span>02</span>Selected publications</h2>
    <div class="profile-grid">
      {% for publication in site_profile.featured_publications %}
      <article class="profile-card">
        <p class="profile-tag">{{ publication.venue }}{% if publication.ranking %} · {{ publication.ranking }}{% endif %}</p>
        <h3>{% if publication.doi %}<a href="{{ publication.doi }}">{{ publication.title }}</a>{% else %}{{ publication.title }}{% endif %}</h3>
        <p>{{ publication.authors }}</p>
      </article>
      {% endfor %}
    </div>
    <p><a class="profile-button" href="{{ site.baseurl }}/publications/">View research record</a></p>
  </section>

  <section class="profile-section">
    <h2><span>03</span>Current research pipeline</h2>
    <ul class="profile-pipeline">
      {% for paper in site_profile.pipeline limit:5 %}
      <li>
        <h3>{{ paper.title }}</h3>
        <p>{{ paper.authors }}</p>
        <span class="profile-status">{{ paper.status }}</span>
        <span class="profile-status">{{ paper.venue }}{% if paper.ranking %} · {{ paper.ranking }}{% endif %}</span>
        {% if paper.note %}<p>{{ paper.note }}</p>{% endif %}
      </li>
      {% endfor %}
    </ul>
  </section>

  <section class="profile-section profile-two-column">
    <div>
      <h2><span>04</span>Teaching</h2>
      <p>{{ site_profile.teaching.overview }}</p>
      <p><a class="profile-button" href="{{ site.baseurl }}/teaching/">Teaching experience</a></p>
    </div>
    <div>
      <h2><span>05</span>Service &amp; tools</h2>
      <p>Academic service, research co-supervision, and open research tools support my research and teaching practice.</p>
      <p><a class="profile-button" href="{{ site.baseurl }}/service/">Service &amp; tools</a></p>
    </div>
  </section>
</div>
