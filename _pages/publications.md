---
layout: single
title: "Publications"
permalink: /publications/
author_profile: true
classes: wide
---

<p>See also my <a href="https://scholar.google.com/citations?user=YOUR_ID">Google Scholar</a> profile.</p>

{% for pub in site.data.publications %}
<div class="pub-entry">
  <div class="pub-badge-col">
    <span class="pub-badge badge-{{ pub.badge }}">{{ pub.venue }}</span>
  </div>
  <div class="pub-content">
    <div class="pub-title">{{ pub.title }}</div>
    <div class="pub-authors">{% for author in pub.authors %}{% if author.me %}<span class="pub-me">{{ author.name }}</span>{% elsif author.url %}<a href="{{ author.url }}">{{ author.name }}</a>{% else %}{{ author.name }}{% endif %}{% unless forloop.last %}, {% endunless %}{% endfor %}{% if pub.alphabetical %} <span class="pub-note">(alphabetical)</span>{% endif %}</div>
    {% if pub.note %}<div class="pub-venue-info">{{ pub.note }}</div>{% endif %}
    <div class="pub-venue-full">{{ pub.venue_full }}, {{ pub.year }}</div>
    {% if pub.award %}<div><span class="pub-award">{{ pub.award }}</span></div>{% endif %}
    {% if pub.links %}
    <div class="pub-links">
      {% for link in pub.links %}
      <a href="{{ link.url }}" class="pub-link">{{ link.label }}</a>
      {% endfor %}
    </div>
    {% endif %}
  </div>
</div>
{% endfor %}
