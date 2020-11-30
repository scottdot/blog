---
layout: dark
title: About
example: Example text in this variable.
---

Here's where you can learn all about the glorious {{ site.title }} by {{ site.author.name }}.
{{ page.example }}

## What is Haiku?

This is where we will be bringing in our first ever include file from our Jekyll project.

{% include big-cat.html %}

## Why New Mexico?

Let's display some data next from a CSV file within our project. The nerd in me is excited.

{% for animal in site.data.animals %}
- The {{ animal.name }} is a {{ animal.size }} animal that is {{ animal.color }}.
{% endfor %}

## Large Animals!

{% for animal in site.data.animals %}
{% if animal.size == "large" %}- <strong style="color: {{ animal.color }};">{{ animal.name }}</strong>
{% else %}- <small>{{ animal.name }}</small>
{% endif %}
{% endfor %}

## Small Animals Get Some Love

{% assign small_animals = site.data.animals | where: "size", "small" %}
{% for animal in small_animals %}
- {{ animal.name | upcase }}
{% endfor %}

