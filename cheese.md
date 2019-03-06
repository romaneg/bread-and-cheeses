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

In the following image are shown the different varieties of cheeses depending on the steps and processes applied to the milk and curd.

![cheese varieties]({{site.baseurl}}/assets/img/cheese/2019-03/cheese-varieties.png)

*Source: On Food and Cooking: The Science and Lore of the Kitchen, Harold McGee*

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
			  <img src="{{ post.image | prepend: site.baseurl}}">
			</a>
		  </div>
		  {% endif %}
		  <div class="post-entry">
            <!--{{ post.excerpt | strip_html | xml_escape | truncatewords: site.excerpt_length }}
            {% assign excerpt_word_count = post.excerpt | number_of_words %}-->
            {% if post.content contains '<!--excerpt.start-->' and post.content contains '<!--excerpt.end-->' %}
                {{ ((post.content | split:'<!--excerpt.start-->' | last) | split: '<!--excerpt.end-->' | first) | strip_html | truncatewords: site.excerpt_length }}
            {% else %}
                {{ post.content | strip_html | truncatewords: site.excerpt_length }}
            {% endif %}
            
            
            {% if post.content != post.excerpt or excerpt_word_count > site.excerpt_length %}
              <a href="{{ post.url | prepend: site.baseurl }}" class="post-read-more">[Read&nbsp;More]</a>
            {% endif %}
          </div>
		</div>

	   </article>
	  {% endif %}
  {% endfor %}
</div>

