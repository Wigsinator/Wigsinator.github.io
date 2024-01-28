---
title: Blog
---
## CSC290 blog posts

As part of CSC290: Communication for Computer Scientists, we were required to maintain a blog for the duration of the class. The blog posts are being kept here for posterity, but no new ones are being created as of right now.

{% for post in site.posts -%}
- [{{ post.title }} - {{ post.date | date_to_string }}]({{ post.url }})
{% endfor -%}