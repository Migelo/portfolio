---
layout: page
permalink: /repositories/
title: repositories
description:
nav: true
nav_order: 3
---

## GitHub users

{% if site.data.repositories.github_users %}
<div class="repositories d-flex flex-wrap flex-md-row flex-column justify-content-between align-items-center">
  {% for user in site.data.repositories.github_users %}
    {% include repository/repo_user.html username=user %}
  {% endfor %}
</div>

---

{% if site.repo_trophies.enabled %}
{% for user in site.data.repositories.github_users %}
  {% if site.data.repositories.github_users.size > 1 %}
  <h4>{{ user }}</h4>
  {% endif %}
  <div class="repositories d-flex flex-wrap flex-md-row flex-column justify-content-between align-items-center">
  {% include repository/repo_trophies.html username=user %}
  </div>

  ---

{% endfor %}
{% endif %}
{% endif %}

## GitHub Repositories

{% if site.data.repositories.github_repos %}
<div class="repositories d-flex flex-wrap flex-md-row flex-column justify-content-between align-items-center">
  {% for repo in site.data.repositories.github_repos %}
    {% include repository/repo.html repository=repo %}
  {% endfor %}
</div>
{% endif %}


## Bitbucket Repositories

<div class="repositories d-flex flex-wrap flex-md-row flex-column justify-content-between align-items-center">
<p> <a href="https://bitbucket.org/Migelo/gpu_testbed/" target="_blank">TENETgpu</a>: main code developed throughout my PhD.</p>
<p> <a href="https://bitbucket.org/Migelo/trace_pygad/" target="_blank">trace_pygad</a>: pygad wrapper used to trace gas clouds through time in GADGED simulations.</p>
</div>
