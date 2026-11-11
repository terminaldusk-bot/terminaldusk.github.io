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
      <span class="artist-index__name">{{ artist.artist }}</span>
      {% if artist.location %}<span class="artist-index__location">{{ artist.location }}</span>{% endif %}
    </a>
  </li>
{% endfor %}
</ul>
