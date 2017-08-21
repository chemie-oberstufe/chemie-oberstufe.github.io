---
title: 2.1 Chemische Bindung
layout: page
showinmenu: false
tags: [thema]
---

## Checkliste

Ich kann ...

| Lernziel | Selbsteinschätzung <br />Einstieg | Materialien | Übungen | Selbsteinschätzung <br />Ausstieg |
| ---   | ---      | ---         | ---     | ---      |
| Merkmale der Bindungsarten in einer Übersicht darstellen und an Beispielen erläutern | | | | |
| das Struktur-Eigenschaften-Basiskonzepts an Beispielen zu allen Bindungsarten anwenden| | | | |
| den Unterschied zwischen chemischer Bindung und zwischenmolekularen Wechselwirkungen erläutern | | | | |
| den räumlichen Bau von Molekülen aus der Strukturformel ableiten | | | | |
| Merkmale der Bindungsarten in einer Übersicht darstellen und an Beispielen erläutern | | | | |

## Fachbegriffe und Konzepte

- Metallbindung
	- elektrostatische Anziehungskräfte
	- Metallgitter
- Ionenbindung
	- elektrostatische Anziehungskräfte
	- Ionen
	- Ionengitter
- Atombindung (polar/unpolar)
	- gemeinsame Elektronenpaare
	- Valenzstrichformeln anorganischer und organischer Moleküle
	- Geometrie von Molekülen, VSEPR-Modell
	- Polarität von Bindungen, Delta-EN-Wert
	- Dipolmoleküle
- Eigenschaften
    - Schmelz- und Siedetemperaturen
    - Löslichkeit, Dissoziation
    - Polarität von Molekülen
- Wasserstoffbrücken, van-der-Waals-Kräfte
- chemische Bindung vs. zwischenmolekulare Kräfte
- stabile Elektronenkonfigurationen
- Struktur-Eigenschaften-Basiskonzept

## Experimente
	
{% assign tag_seite = "chemische-bindung" %}

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

<ul class="tags">
	<li class="tag">{{ tag_seite }}</li>
</ul>
<ul>
{% assign pages = site.pages | sort: 'title' %}
{% for page in pages %}
	 {% if page.tags contains tag_seite %}
	 <li>
	 <a href="{{ page.url }}">{{ page.title }}</a>
	 {% for tag in page.tags %}
		 <a class="tag" href="/tags/{{ tag | slugify }}">{{ tag }}</a>
	 {% endfor %}
	 </li>
	 {% endif %}
{% endfor %}
</ul>

## Materialien

- [Simple Chemics: Atombindung](https://www.youtube.com/watch?v=IYjMICnDK50)
- [Simple Chemics: Polare und unpolare Atombindung](https://www.youtube.com/watch?v=_KLbBgW32V)
- [Simple Chemics: Lewis-Formel und Oktettregel](https://www.youtube.com/watch?v=5tbY6cRd5HE)
- [Simple Chemics: Die Wertigkeit der Elemente](https://www.youtube.com/watch?v=aZbXqTqP0GE)
- [Simple Chemics: Metallische Bindung](https://www.youtube.com/watch?v=Z6L8LD4EV3w)
- [Simple Chemics: Ionenbildung](https://www.youtube.com/watch?v=cFP69D20MMQ)
- [Simple Chemics: Ionenbindung](https://www.youtube.com/watch?v=j6B33FTQyqg)
- Zwischenmolekulare Kräfte
	- [Simple Chemics: Van der Waals-Kräfte](https://www.youtube.com/watch?v=bXHor4n67Dg)
	- [Simple Chemics: Dipol-Dipol-Wechselwirkungen](https://www.youtube.com/watch?v=zKvHQ9QplWY)
	- [Simple Chemics: Wasserstoffbrücken](https://www.youtube.com/watch?v=En2hkTeICrc)






