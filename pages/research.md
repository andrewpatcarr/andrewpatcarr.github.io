---
layout: single
title: "Research"
permalink: /research/
# entries_layout: grid
author_profile: true
# classes: wide
---

<style>
.entries-grid {
  display: flex;
  flex-wrap: wrap;
  margin: -1%;
}
.archive__item {
  flex: 0 0 48%;
  max-width: 48%;
  margin: 1%;
  border-radius: 8px;
  /* background:rgb(0, 0, 0); */
  padding: 5px;
}
.archive__item img {
  width: 100%;
  height: auto;
  border-radius: 8px;
}
</style>


<div class="entries-grid">
  {% assign sorted_projects = site.research | sort: 'order' %}
  {% for project in sorted_projects %}
    <div class="archive__item">
      {% if project.header.teaser %}
        <a href="{{ project.url | relative_url }}">
          <img src="{{ project.header.teaser | relative_url }}" alt="{{ project.title }}">
        </a>
      {% endif %}
      <a href="{{ project.url | relative_url }}" style=" text-decoration: none;">  
        <h2>
        
          {{ project.title }}
        
        </h2>
      <p style="color: black; text-decoration: none;">
        {{ project.excerpt }}
      </p>
      </a>
    </div>
  {% endfor %}
</div>