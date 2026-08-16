---
layout: single
title: ""
permalink: /service/
author_profile: false
classes: wide profile-page
---

{% assign site_profile = site.data.site_profile %}
{% include site-profile-styles.html %}

<div class="profile-shell">
  <header class="profile-cv-header">
    <p class="profile-eyebrow">Academic contribution</p>
    <h1>Service &amp; research tools</h1>
    <p class="profile-lead">Service, co-supervision, and transparent research tooling complement my research and teaching practice.</p>
  </header>

  <section class="profile-section profile-two-column">
    <div>
      <div class="profile-section-heading">
        <p class="profile-section-kicker">Service</p>
        <h2>Academic contribution</h2>
      </div>
      <ul class="profile-detail-list">
        {% for item in site_profile.service_tools.service %}
        <li>
          <h3>{{ item.title }}</h3>
          <p class="profile-item-meta">{{ item.period }}</p>
          <p class="profile-item-summary">{{ item.detail }}</p>
        </li>
        {% endfor %}
      </ul>
    </div>
    <div>
      <div class="profile-section-heading">
        <p class="profile-section-kicker">Tools</p>
        <h2>Open research software</h2>
      </div>
      <ul class="profile-detail-list">
        {% for tool in site_profile.service_tools.tools %}
        <li>
          <h3><a href="{{ tool.url }}">{{ tool.name }}</a></h3>
          <p class="profile-item-summary">{{ tool.detail }}</p>
        </li>
        {% endfor %}
      </ul>
    </div>
  </section>
</div>
