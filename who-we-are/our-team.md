---
layout: node
title: Our Team
parent: who-we-are
---

Multicultural, multilingual, and multidisciplinary to the core—global in outlook and approach—DAI’s technical leaders are steeped in the challenges of delivering development solutions in the field. They are committed to sharing our innovation and experience to inform international development practices worldwide.

<hr>
{% include _who-we-are/experts-filter.html %}
{% for expert in site.experts %}
<div class="experts-rail">
  <div class="people-block">
    <img src="{{expert.photo}}" alt="" class="expert-details--photo">
    <div class="expert-details--metadata">
      <h3>{{ expert.title }}</h3>
        <p class="expert-details--expertise">
      {% for expertise in expert.expertise %}
        {% for solution in site.data.solutions %}
          {% if expertise == solution.text %}
            <a class="href="">{{ solution.icon }} {{ solution.text }}</a>
          {% endif %}
        {% endfor %}
      {% endfor %}
      {% for locale in expert.regions %}
        <p class="expert-details--regions">
          {% for region in site.data.regions %}
            {% if locale == region.text %}
            <a class="href="">{{ region.icon }} {{ region.text }}</a>
          {% endif %}
        {% endfor %}
        </p>
      {% endfor %}
    </div>
    <div class="expert-summary">
      <p class="expert-details--title">{{ expert.job-title }}</p>
      <p>{{ expert.summary }}</p>
    </div>
    <a href="{{ expert.url }}" class="primary-block--button expert-button">Read More <svg class="redirect" viewBox="0 0 36 70" preserveAspectRatio="xMinYMax meet"><use xlink:href="#redirect"></use></svg></a>
  </div>
  <hr>
</div>
{% endfor %}