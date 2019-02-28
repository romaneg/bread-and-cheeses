---
layout: page
title: Let's make some cheese!
---

---
### What is cheese?

The origin of cheese is very likely to be as old as the beginning of agriculture and farming. People rapidly discovered it was a good way of preserving milk in an eatable form.
Cheese is a product made of one single product: milk. Milk is coagulated to remove a large part of its water content. This coagulation is the result of its own fermentation and the addition of rennet (animal or vegetal enzymes) or other acid (i.e. vinegar).
Cheese making counts generally three steps:
1. Coagulation (milk acidification and separation of curd and lactoserum)
2. Draining and shaping
3. Ripening, development

### Why making cheese is an art?

The variety of cheeses is huge (France on its own counts more than 1,200 different types of cheeses!). It is impressive as only one product can transform to so many different forms. 
Cheese development depends on multiple parameters:
- milk quality
- ferments (type and diversity of bacterias, yeast)
- *terroir* (French word designating the local environment)
- temperature
- humidity

# Last articles
---

<div class="posts-list">
  {% for post in site.posts %}
	  {% if post.tags contains "cheese" %}
	  <article class="post-preview">
		<a href="{{ post.url | prepend: site.baseurl }}">
		  <h2 class="post-title">{{ post.title }}</h2>

		  {% if post.subtitle %}
		  <h3 class="post-subtitle">
			{{ post.subtitle }}
		  </h3>
		  {% endif %}
		</a>

		<p class="post-meta">
		  Posted on {{ post.date | date: "%B %-d, %Y" }}
		</p>

		<div class="post-entry-container">
		  {% if post.image %}
		  <div class="post-image">
			<a href="{{ post.url | prepend: site.baseurl }}">
			  <img src="{{ post.image }}">
			</a>
		  </div>
		  {% endif %}
		  <div class="post-entry">
				{{ post.excerpt | strip_html | xml_escape | truncatewords: site.excerpt_length }}
		  </div>
		</div>

	   </article>
	  {% endif %}
  {% endfor %}
</div>

