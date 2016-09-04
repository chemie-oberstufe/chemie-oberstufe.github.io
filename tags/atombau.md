---
title: Seiten getaggt mit "Atombau"
layout: page
showinmenu: false
---

{% comment %}
=======================
The purpose of this snippet is to list all your posts posted with a certain tag.
=======================
{% endcomment %}
{% for tag in tags %}
	<h2 id="{{ tag | slugify }}">{{ tag }}</h2>
	<ul>
	 {% for page in site.pages %}
		 {% if page.tags contains tag %}
		 <li>
		 <h3>
		 <a href="{{ page.url }}">
		 {{ page.title }}
		 <small>{{ page.date | date_to_string }}</small>
		 </a>
		 {% for tag in page.tags %}
			 <a class="tag" href="/tags/index#{{ tag | slugify }}">{{ tag }}</a>
		 {% endfor %}
		 </h3>
		 </li>
		 {% endif %}
	 {% endfor %}
	</ul>
{% endfor %}
