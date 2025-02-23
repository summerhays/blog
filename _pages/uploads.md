---
title: Uploads
---
{% assign count_me = 1 %}
{% for thing in site.static_files  %}
  {% if thing.path contains 'assets/upload'  %}
    {% assign filext = thing.extname | downcase %}

[{{ count_me }}: ```{{ thing.name }}```]({{ thing.path }})  

    {% if filext == ".jpg" or filext == ".png" or filext == ".avif" or filext == ".jpeg" or filext == ".webp" %}

![# {{ count_me }}]({{ thing.path  }})
    {% endif %}
      {% assign count_me = count_me | plus: 1 %}
  {% endif  %}
{% endfor  %}
