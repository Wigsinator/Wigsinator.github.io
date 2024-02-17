---
title: Blog
---
## General Blog Posts

{% for post in site.posts -%}
	{%- if post.category != "csc290" -%}
- [{{ post.title }} - {{ post.date | date_to_string }}]({{ post.url }})
	{%- endif -%}
{% endfor %}

## CSC290 blog posts

As part of CSC290: Communication for Computer Scientists, we were required to maintain a blog for the duration of the class. The blog posts are being kept here for posterity, but their quality is questionable, and their subject matter was defined moreso by the assignment than by.

{% for post in site.categories.csc290 -%}
- [{{ post.title }} - {{ post.date | date_to_string }}]({{ post.url }})
{% endfor -%}