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
    <div class="profile-section-heading">
      <p class="profile-section-kicker">01</p>
      <h2>Research profile</h2>
    </div>
    <p class="profile-lead">{{ site_profile.profile.research_statement }}</p>
    <p class="profile-meta"><strong>Methods:</strong> {{ site_profile.profile.methods }}<br><strong>Doctoral status:</strong> {{ site_profile.profile.doctoral_status }}</p>
  </section>

  <section class="profile-section">
    <div class="profile-section-heading">
      <p class="profile-section-kicker">02</p>
      <h2>Selected publications</h2>
    </div>
    <div class="profile-grid">
      {% for publication in site_profile.featured_publications %}
      <article class="profile-card">
        <p class="profile-publication-venue"><em>{{ publication.journal }}</em>{% if publication.citation %}<span>{{ publication.citation }}</span>{% endif %}</p>
        <h3>{% if publication.doi %}<a href="{{ publication.doi }}">{{ publication.title }}</a>{% else %}{{ publication.title }}{% endif %}</h3>
        <p>{{ publication.authors }}</p>
        {% if publication.ranking %}<span class="profile-publication-rank">{{ publication.ranking }}</span>{% endif %}
      </article>
      {% endfor %}
    </div>
    <p><a class="profile-button" href="{{ site.baseurl }}/publications/">View research record</a></p>
  </section>

  <section class="profile-section">
    <div class="profile-section-heading">
      <p class="profile-section-kicker">03</p>
      <h2>Current research pipeline</h2>
    </div>
    <ul class="profile-pipeline">
      {% for paper in site_profile.pipeline limit:5 %}
      <li>
        <h3>{{ paper.title }}</h3>
        <p>{{ paper.authors }}</p>
        <p class="profile-pipeline-venue"><em>{{ paper.venue }}</em></p>
        <span class="profile-status">{{ paper.status }}</span>
        {% if paper.ranking %}<span class="profile-publication-rank">{{ paper.ranking }}</span>{% endif %}
        {% if paper.note %}<p>{{ paper.note }}</p>{% endif %}
      </li>
      {% endfor %}
    </ul>
  </section>

  <section class="profile-section profile-two-column">
    <div>
      <div class="profile-section-heading">
        <p class="profile-section-kicker">04</p>
        <h2>Teaching</h2>
      </div>
      <p>{{ site_profile.teaching.overview }}</p>
      <p><a class="profile-button" href="{{ site.baseurl }}/teaching/">Teaching experience</a></p>
    </div>
    <div>
      <div class="profile-section-heading">
        <p class="profile-section-kicker">05</p>
        <h2>Service &amp; tools</h2>
      </div>
      <p>Academic service, research co-supervision, and open research tools support my research and teaching practice.</p>
      <p><a class="profile-button" href="{{ site.baseurl }}/service/">Service &amp; tools</a></p>
    </div>
  </section>
</div>
