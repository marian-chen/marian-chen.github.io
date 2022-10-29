---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: true
---

{% if author.googlescholar %}
  You can also find my articles on <u><a href="{{author.googlescholar}}">my Google Scholar profile</a>.</u>
{% endif %}

{% include base_path %}

{% if site.publications_journal.size != 0 %}
## Peer-reviewed conferences and journals:
{% endif %}

{% for post in site.publications_journal reversed %}
  {% include publication.html %}
{% endfor %}

{% if site.publications_workshop.size != 0 %}
## Workshop papers
{% endif %}

{% for post in site.publications_workshop reversed %}
  {% include publication.html %}
{% endfor %}

{% if site.publications_thesis.size != 0 %}
## Thesis
{% endif %}

{% for post in site.publications_thesis reversed %}
  {% include publication.html %}
{% endfor %}