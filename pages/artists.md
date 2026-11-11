---
layout: default
title: Artists
permalink: /artists/
---
# Artists

{% assign artists = site.artists | sort_natural: "artist" %}
<ul class="artist-index">
{% for artist in artists %}
  <li>
    <a href="{{ artist.url | relative_url }}">
      {% if artist.img %}
      <img class="artist-index__thumb" src="{{ "/assets/img/artists/Artist-" | append: artist.slug | append: "-small.jpg" | relative_url }}" alt="" width="48" height="60" loading="lazy">
      {% else %}
      <span class="artist-index__thumb artist-index__thumb--empty" aria-hidden="true"><img src="{{ "/assets/img/logo-mark.png" | relative_url }}" alt="" width="40" height="40" loading="lazy"></span>
      {% endif %}
      <span class="artist-index__name">{{ artist.artist }}</span>
    </a>
  </li>
{% endfor %}
</ul>
