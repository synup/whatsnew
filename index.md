---
layout: default
title: Changelog
---

Text 1

{% assign changelog_files = site.static_files | where: "path", "_changelogs" %}
{% assign sorted_changelogs = changelog_files | sort: "name" %}

{% for file in sorted_changelogs %}
  {% assign changelog_date = file.name | slice: 0, 16 %}
  {% assign changelog_content = file.contents | markdownify %}

  <details>
    <summary>{{ changelog_date }}</summary>
    {{ changelog_content }}
  </details>
{% endfor %}