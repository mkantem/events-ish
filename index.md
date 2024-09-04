---
layout: default
title: "Evenements ISH"
pagination:
  enabled: true
  per_page: 5
  permalink: /page:num/
---

## Parcourez nos événements à venir et passés organisés à l'Institut des Sciences Humaines.

## Événements à venir

<ul>
  {% assign current_date = site.time | date: "%Y-%m-%d" %}
  {% for post in paginator.posts %}
    {% if post.date > current_date %}
      <li>
        <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
        <p>{{ post.excerpt }}</p>
      </li>
    {% endif %}
  {% endfor %}
</ul>

<div class="pagination">
  {% if paginator.previous_page %}
    <a href="{{ paginator.previous_page_path }}">Previous</a>
  {% endif %}
  {% if paginator.next_page %}
    <a href="{{ paginator.next_page_path }}">Next</a>
  {% endif %}
</div>

## Événements précédents

<ul>
  {% for post in site.posts %}
    {% if post.date <= current_date %}
      <li>
        <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
        <p>{{ post.excerpt }}</p>
      </li>
    {% endif %}
  {% endfor %}
</ul>
