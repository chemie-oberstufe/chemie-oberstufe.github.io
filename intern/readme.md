---
title: README
layout: page
showinmenu: false
---

## includes

**Grafiken, einfach, mit Dateiendung**

```
	include img name="" alt="" width=""
```

**Grafiken, figure, mit Dateiendung**

```
	include figure name="" caption="" alt="" width=""
```

**GHS-Symbole, ohne Dateiendung**

```
	include ghs name="ätzend,gesundheitsgefährdend,..."
```

## Tags

- im YAML-Block: tags: [thema, atombau, basics]
- zu jedem verwendeten Tag sollte eine Seite tags/name_des_tags.md existieren
 - diese Seite listet alle Seiten mit Tag "name_des_tags" auf
 - in dieser Seite sind die beiden ersten Teile immer gleich -> Logik, Tags auslesen etc.
 - der Titel und die Variable nach dem YAML-Block muss geändert werden: <pre>{% assign tag = "name_des_tags" %}</pre>
