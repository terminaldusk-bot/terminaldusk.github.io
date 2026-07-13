---
layout: default
title: Artists
permalink: /artists/
---
# Artists 
   
   
  {% for artist in site.artists %}
  <div class="item-artist">
 <a href="{{ artist.url }}">
 <img src="/assets/img/artists/Artist-{{ artist.artist | downcase | replace: ' ', '' }}-small.jpg">
  <h2>{{ artist.artist }}</h2>
  <p>{{ artist.location }}</p>
  <p>{{ artist.genres | join: ", " }}</p>
  </a>
  </div>
{% endfor %}
           