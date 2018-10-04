---
layout: home
order: 0
title: About Me
---

<div id="featuredprojects" class="my-5 d-flex flex-column flex-lg-row align-items-center align-items-lg-stretch">
	<div class="m-auto">
		<h1 class="m-0 p-3 text-center" style="min-width:7em">
			About Me
		</h1>
	</div>
	
	<div class="p-lg-1 mx-lg-3 sepbar"></div>
	
  <p class="p-1 pl-lg-4">
test
</p>
</div>

<hr>

<div id="featuredprojects" class="my-5 d-flex flex-column flex-lg-row-reverse align-items-center align-items-lg-stretch">
	<div class="m-auto">
		<h1 class="m-0 p-3 text-center" style="min-width:7em">
			<a href="projects.html">Featured Projects</a>
		</h1>
	</div>

	<div class="p-lg-1 mx-lg-3 sepbar"></div>


  <div>

    {% assign sorted = site.projects | reverse %}
    {% for project in sorted %}
    {% if project.featured %}
      {% assign item = project %}
      {% include projectbox.html %}
    {% endif %}
    {% endfor %}

  </div>

</div>
  
<hr>

<div id="latestposts" class="my-5 d-flex flex-column flex-lg-row align-items-center align-items-lg-stretch">

  <div class="m-auto">
		<h1 class="m-0 p-3 text-center" style="min-width:7em">
			<a href="post.html">Latest Posts</a>
		</h1>
	</div>

	<div class="p-lg-1 mx-lg-3 sepbar"></div>


  <div>

    {% for p in site.posts limit:2 %}
      {% assign item = p %}
      {% include postbox.html %}
    {% endfor %}
  
  </div>

  
</div>
