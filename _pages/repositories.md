---
layout: page
permalink: /repositories/
title: Repositories
description:
nav: true
nav_order: 5
profile:
  image: repo-profile.png
  image_circular: false # crops the image to make it circular
  caption: "A portrait by my (former) mentee Gloria Lin."
---

{% if site.data.repositories.github_users %}
<div class="repositories d-flex flex-wrap flex-md-row flex-column justify-content-between align-items-center">
  {%- if page.profile.image %}
  <div class="repo-profile">
    {%- assign profile_image_path = page.profile.image | prepend: 'assets/img/' -%}
    {% if page.profile.image_circular %}
      {%- assign profile_image_class = "img-fluid rounded-circle" -%}
    {% else %}
      {%- assign profile_image_class = "img-fluid rounded" -%}
    {% endif %}
    {% include figure.html
    path=profile_image_path
    class=profile_image_class
    caption=page.profile.caption
    alt=page.profile.image -%}
  </div>
  {% endif -%}

  {% for user in site.data.repositories.github_users %}
    {% include repository/repo_user.html username=user %}
  {% endfor %}
</div>
{% endif %}

---

{% if site.data.repositories.github_repos %}
<div class="repositories d-flex flex-wrap flex-md-row flex-column justify-content-between align-items-center">
  {% for repo in site.data.repositories.github_repos %}
    {% include repository/repo.html repository=repo %}
  {% endfor %}  
</div>
{% endif %}
