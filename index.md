---
layout: default
title: "Evenements ISH"
pagination: true
---

## Parcourez nos événements à venir et passés organisés par l'Institut des Sciences Humaines.

## Événements à venir

<ul>
  {% assign current_date = site.time | date: "%Y-%m-%d" %}
  {% for post in site.posts %}
    {% assign post_date = post.date | date: "%Y-%m-%d" %}
    {% if post_date > current_date %}
      <li>
        <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
        <p>{{ post.excerpt }}</p>
      </li>
    {% endif %}
  {% endfor %}
</ul>

## Événements précédents

<ul>
  {% for post in site.posts %}
    {% assign post_date = post.date | date: "%Y-%m-%d" %}
    {% if post_date <= current_date %}
      <li>
        <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
        <p>{{ post.excerpt }}</p>
      </li>
    {% endif %}
  {% endfor %}
</ul>

