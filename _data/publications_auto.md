---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: true
---


You can also find my publications on my [Google Scholar profile](https://scholar.google.com/citations?user=EDDQMfgAAAAJ&hl=fr&oi=sra).



{% include base_path %}

{% for post in site.publications reversed %}
  {% include archive-single.html %}
{% endfor %}
