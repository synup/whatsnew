---
layout: default
title: Changelog
---

{% for changelog in site.data.changelogs %}
  {% assign changelog_content = site.pages | where: "path", changelog.path | first %}
  {% if changelog.show_month %}
# {{ changelog.month }}
  <br/>
  {% endif %}
  <details>
    <summary>{{ changelog.summary }}</summary>
    {{ changelog_content.content | markdownify }}
  </details>
  <br/>
{% endfor %}