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
<div class="repositories d-flex flex-wrap flex-md-row flex-column align-items-stretch">
  {% for user in site.data.repositories.github_users %}
    {% include repository/repo_user.html username=user %}
  {% endfor %}
</div>
{% endif %}

## GitHub Repositories

{% if site.data.repositories.github_repos %}
<div class="repositories d-flex flex-wrap flex-md-row flex-column align-items-stretch">
  {% for repo in site.data.repositories.github_repos %}
    {% include repository/repo.html repository=repo.repo description=repo.description %}
  {% endfor %}
</div>
{% endif %}

## Bitbucket Repositories

<div class="repositories d-flex flex-wrap flex-md-row flex-column align-items-stretch">
  <div class="repo p-3">
    <a href="https://bitbucket.org/Migelo/gpu_testbed/" target="_blank" rel="external nofollow noopener">
      <h5 class="repo-title"><i class="fab fa-bitbucket"></i> TENETgpu</h5>
    </a>
    <p class="repo-description">main code developed throughout my PhD.</p>
  </div>
  <div class="repo p-3">
    <a href="https://bitbucket.org/Migelo/trace_pygad/" target="_blank" rel="external nofollow noopener">
      <h5 class="repo-title"><i class="fab fa-bitbucket"></i> trace_pygad</h5>
    </a>
    <p class="repo-description">pygad wrapper used to trace gas clouds through time in GADGED simulations.</p>
  </div>
</div>
