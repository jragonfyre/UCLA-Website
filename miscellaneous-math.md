---
layout: default
title: Miscellaneous Math
---

# Miscellaneous Math

This page collects miscellaneous calculations
and mathematical exposition that I decided to write up.

{% assign math_posts = site.posts | where: 'math', true %}
{% for post in math_posts %}
{% include math_post_summary.md post=post %}
{% endfor %}