---
layout: archive
title: "Working Papers"
permalink: /working_papers/
author_profile: true
---

{% include base_path %}

{% for post in site.working_papers%}
  <div class="archive__item">
    <h2 class="archive__item-title">
      <a href="{{ post.url }}">{{ post.title }}</a>
      {% if post.job_market_paper %}
        <div class="label label-primary">Job Market Paper</div>
      {% endif %}
    </h2>
    {% if post.authors %}
      <p>Authors: {{ post.authors }}</p>
    {% endif %}
    {% if post.abstract %}
      <p class="archive__item-excerpt">{{ post.abstract }}</p>
    {% endif %}
    {% if post.paperurl %}
      <p><a href="{{ post.paperurl }}">Download Paper</a></p>
    {% endif %}
  </div>
{% endfor %}


   