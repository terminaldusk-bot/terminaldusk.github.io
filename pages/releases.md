---
layout: default
title: Releases
permalink: /releases/
---
# Releases 

<div class="release-grid">

{% assign releases = site.releases | sort: "cat_num" | reverse %}

  {% for release in releases %}
  <div class="item-release">
 <a href="{{ release.url }}">
 <img src="/assets/img/releases/Release-{{ release.img | replace: ' ', '' }}.png">
  <!-- <p>{{ release.artists }}</p> -->

<p class="release-artist">
{% assign artist_count = release.artists | size %}

{% if artist_count == 0 %}
  Various Artists

{% elsif artist_count == 2 %}

  {% assign artist_one_slug = release.artists[0] %}
  {% assign artist_two_slug = release.artists[1] %}

  {% assign artist_one = site.artists | where: "slug", artist_one_slug | first %}
  {% assign artist_two = site.artists | where: "slug", artist_two_slug | first %}

  {{ artist_one.artist }} / {{ artist_two.artist }}

{% elsif artist_count == 1 %}

  {% assign artist_slug = release.artists[0] %}
  {% assign artist = site.artists | where: "slug", artist_slug | first %}

  {{ artist.artist }}

{% endif %}
</p>

  
  <h2 class="release-title">{{ release.title }}</h2>  
  <p class="release-cat">{{ release.cat }}</p>
    
  </a>
  {% if release.bandcamp_buy %}
             <p><a href="{{release.bandcamp_buy}}" class="link-buy-bandcamp">Buy on Bandcamp</a></p>
              {% endif %}
  </div>
{% endfor %}
           
           </div>