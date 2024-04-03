---
layout: archive
title: "Projects"
permalink: /projects/
author_profile: true
---

{% include base_path %}

## Open Source Code for My Publications
{% for post in site.projects-pubs %}
    {% include archive-single.html %}
  {% endfor %}

## Data Science Projects

A collection of projects completed during MSc Data Science.
{% for post in site.projects-ds %}
    {% include archive-single.html %}
  {% endfor %}
  
## Machine Learning Projects

A collection of machine learning projects completed during MSc Data Science and just for fun!
{% for post in site.projects-ml %}
    {% include archive-single.html %}
  {% endfor %}

## Other Projects

A collection of other projects that are just for fun! 
{% for post in site.projects-other %}
    {% include archive-single.html %}
  {% endfor %}
