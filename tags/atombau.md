---
title: Seiten getaggt mit "Atombau"
layout: page
showinmenu: false
---

{% comment %}
=======================
The following part extracts all the tags from your posts and sort tags, so that you do not need to manually collect your tags to a place.
=======================
{% endcomment %}
{% assign rawtags = "" %}
{% for page in site.pages %}
	{% assign ttags = page.tags | join:'|' | append:'|' %}
	{% assign rawtags = rawtags | append:ttags %}
{% endfor %}
{% assign rawtags = rawtags | split:'|' | sort %}

{% comment %}
=======================
The following part removes duplicated tags and invalid tags like blank tag.
=======================
{% endcomment %}
{% assign tags = "" %}
{% for tag in rawtags %}
	{% if tag != "" %}
		{% if tags == "" %}
			{% assign tags = tag | split:'|' %}
		{% endif %}
		{% unless tags contains tag %}
			{% assign tags = tags | join:'|' | append:'|' | append:tag | split:'|' %}
		{% endunless %}
	{% endif %}
{% endfor %}


{% comment %}
=======================
The purpose of this snippet is to list all your posts posted with a certain tag.
=======================
{% endcomment %}

{% assign tag = "atombau" %}
<ul class="tags">
	<li class="tag">{{ tag }}</li>
</ul>
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
