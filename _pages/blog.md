---
title: Blog
---
## General Blog Posts

I've decided that I want to start using this site more, so I'm gonna be maintaining this blog. I hope that having long-form writings on various topics will help me practice both critical thinking and help reverse the irony poisoning that comes from being terminally online. The goal is to post something every Saturday, and the topic will really be whatever I want it to be that week. 

{% for post in site.posts -%}
	{%- if post.category != "csc290" %}
- [{{ post.title }} - {{ post.date | date_to_string }}]({{ post.url }})
	{%- endif -%}
{% endfor %}

## CSC290 blog posts

As part of CSC290: Communication for Computer Scientists, we were required to maintain a blog for the duration of the class. The blog posts are being kept here for posterity, but their quality is questionable, and their subject matter was defined moreso by the assignment than by.

{% for post in site.categories.csc290 -%}
- [{{ post.title }} - {{ post.date | date_to_string }}]({{ post.url }})
{% endfor -%}