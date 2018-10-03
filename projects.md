---
title:  Projects
order: 1
layout: default

---
<div id="allprojects" class="d-flex flex-wrap justify-content-between">
{% assign sorted = site.projects | reverse %}
{% for project in sorted %}
{% assign item = project %}
{% include projectbox.html %}
{% endfor %}
</div>
