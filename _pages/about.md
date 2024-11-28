---
permalink: /
title: "Roman Nigmatullin"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

I'm a machine learning researcher and engineer in Yandex Lavka, specializing in deep learning and recommender systems. My interests also include information retrieval, self-driving cars and large-scale data processing, and I have a background in software engineering and product analytics during my work at Yandex.

I'm pursuing Master's degree in Applied Math and Computer Science at HSE University and Yandex School of Data Analysis joint program. I hold a Bachelor of Science in Applied Math at HSE University with specialty in stochastic processes and probability theory.

{% for collection in site.collections %}
{% unless collection.output == false or collection.label == "posts" %}
  {% capture label %}{{ collection.label }}{% endcapture %}
  {% if label != written_label %}
  <h2>{{ label }}</h2>
  {% capture written_label %}{{ label }}{% endcapture %}
  {% endif %}
{% endunless %}
{% for post in collection.docs %}
  {% unless collection.output == false or collection.label == "posts" %}
  {% include archive-single.html %}
  {% endunless %}
{% endfor %}
{% endfor %}
