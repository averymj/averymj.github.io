---
layout: page
permalink: /repositories/
title: repositories
description: Check out my Github profile and repositories!
nav: true
nav_order: 4
---

{% if site.data.repositories.github_users %}

{% assign user = site.data.repositories.github_users[0] %}

<div class="card p-4 mb-4 text-center">

  <h3>{{ user }}</h3>

  <p class="text-muted">
    GitHub Profile
  </p>

  <a href="https://github.com/{{ user }}" target="_blank" class="btn btn-outline-primary btn-sm">
    Visit Profile →
  </a>

</div>

## GitHub users

<div class="repositories d-flex flex-wrap flex-md-row flex-column justify-content-between align-items-center">
  {% for user in site.data.repositories.github_users %}
    <a href="https://github.com/{{ user }}" target="_blank" rel="noopener">
      <div class="card p-3 text-center">
        <strong>{{ user }}</strong>
        <p class="text-muted mb-0">GitHub Profile</p>
      </div>
    </a>
  {% endfor %}
</div>

---

{% if site.repo_trophies.enabled %}
{% for user in site.data.repositories.github_users %}
{% if site.data.repositories.github_users.size > 1 %}

  <h4>{{ user }}</h4>
  {% endif %}
  <div class="repositories d-flex flex-wrap flex-md-row flex-column justify-content-between align-items-center">
  {% include repository/repo_trophies.liquid username=user %}
  </div>

---

{% endfor %}
{% endif %}
{% endif %}

{% if site.data.repositories.github_repos %}

## GitHub Repositories

<div class="repositories d-flex flex-wrap flex-md-row flex-column justify-content-between align-items-center">
  {% for repo in site.data.repositories.github_repos %}
    {% include repository/repo.liquid repository=repo %}
  {% endfor %}
</div>
{% endif %}
