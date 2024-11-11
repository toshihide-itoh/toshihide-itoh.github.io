---
title: tags
layout: page
excerpt: Sorted article by tags.
---

<h2>{{ page.title | capitalize }}.</h2>

{%- for tag in site.tags -%}
  {%- capture name -%}{{ tag | first }}{%- endcapture -%}
  <p id="{{ name }}" class="archive-index">{{ name | downcase }}</p>
  {%- for post in site.tags[name] -%}
    <ul>
      <li>
        <span class="archive-date">{{ post.date | date: "%Y/%m/%d: " }}</span>
        <span class="archive-title"><a href="{{ post.url }}">{{ post.title | escape }}</a></span>
      </li>
    </ul>
  {%- endfor -%}
{%- endfor -%}
