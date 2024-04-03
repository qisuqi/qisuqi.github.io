---
layout: archive
title: "Projects"
permalink: /projects/
author_profile: true
---

{% include base_path %}

## Open Source Code for My Publications
  <ul>{% for post in site.projects-pubs %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>

## Data Science Projects

A collection of projects completed during MSc Data Science.
  <ul>{% for post in site.projects-ds %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>
  
## Machine Learning Projects

A collection of machine learning projects completed during MSc Data Science and just for fun!
  <ul>{% for post in site.projects-ml %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>

## Other Projects

A collection of other projects that are just for fun! 
  <ul>{% for post in site.projects-other %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>
