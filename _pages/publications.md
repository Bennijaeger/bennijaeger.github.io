---
layout: page
title: titles.publications
description: descriptions.publications
permalink: /publications/
nav: true
nav_order: 2
---

<!-- _pages/publications.md -->

In lattice field theory, author lists are alphabetical, so the author position does not indicate the individual contribution. The [research page](https://bennijaeger.github.io/research/) describes my role in each project. Citation counts are on [INSPIRE-HEP](https://inspirehep.net/authors/1272234) and [Google Scholar](https://scholar.google.com/citations?user=nnHveQwAAAAJ).

<div class="publications">

<h2 class="bibliography-section">Journal articles</h2>
{% bibliography --query @*[category=journal] %}

<h2 class="bibliography-section">Peer-reviewed proceedings</h2>
{% bibliography --query @*[category=proceedings] %}

<h2 class="bibliography-section">Other</h2>
{% bibliography --query @*[category=other] %}

</div>
