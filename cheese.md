---
layout: page
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

