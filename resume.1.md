---
title: Resume
layout: default
order: 3
---

{% for section in site.data.resume.sections %}

<div class="mb-5">
  
{% if forloop.index>1 %}<hr class="mb-5"/>{% endif %}
<h2 class="mb-5 text-uppercase">{{section.name}}</h2>

{% for entry in section.entries %}


<div class="mb-5">
  
<div class="resume-item d-flex flex-column flex-md-row mb-3">
  <div class="resume-content mr-auto">
  <h3 class="m-0 p-0">{{ entry.title }}</h3>
  <h4 class="m-0 p-0">{{ entry.subtitle }}</h4>
  <h5 class="mb-0">{{ entry.tags | join: ' · ' }}</h5>
  </div>
  {% if entry.date != null %}
  <div class="resume-date text-md-right">
    <span class="text-primary">{{entry.date}}<br>
    {{entry.location}}</span>
  </div>
  {% endif %}
</div>

{% if entry.description != null %}
<div class="resume-item d-flex flex-column flex-md-row">
  <div class="resume-content mr-auto">
  <ul>
    {% for desc in entry.description %}
      <li>{{desc}}</li>
    {% endfor %}
  </ul>
  </div>
</div>
{% endif %}

</div>

{% endfor %}

</div>
{% endfor %}
