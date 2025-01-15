---
title: notes
layout: page
---
<h2>{{ page.title | capitalize }}.</h2>


{%- for post in site.posts -%}
  {%- capture current_year -%}{{ post.date | date: "%Y" }}{%- endcapture -%}
  {%- unless current_year == previous_year -%}
    <p class="archive-index">{{ current_year }}</p>
    {%- assign previous_year = current_year -%}
  {%- endunless -%}
  <ul>
    <li>
      <span class="archive-date">{{ post.date | date: "%Y/%m/%d: " }}</span>
      <span class="archive-title"><a href="{{ post.url }}">{{ post.title | escape }}</a></span>
      <blockquote class="archive-excerpt">{{ post.excerpt }}</blockquote>
    </li>
    </ul>
{%- endfor -%}

