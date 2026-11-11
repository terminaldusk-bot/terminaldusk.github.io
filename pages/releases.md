---
layout: default
title: Releases
permalink: /releases/
---
# Releases

{% assign main_releases = site.releases | where_exp: "r", "r.series != 'digital'" | sort: "cat_num" | reverse %}
{% assign digital_releases = site.releases | where: "series", "digital" | sort: "cat_num" | reverse %}

<div class="release-grid">
{% for release in main_releases %}
  {% include catalog-card.html release=release %}
{% endfor %}
</div>

{% if digital_releases.size > 0 %}
<section class="catalog-section" aria-labelledby="digital-heading">
  <h2 class="catalog-heading" id="digital-heading">Terminal Dusk Digital</h2>
  <div class="release-grid">
  {% for release in digital_releases %}
    {% include catalog-card.html release=release %}
  {% endfor %}
  </div>
</section>
{% endif %}
