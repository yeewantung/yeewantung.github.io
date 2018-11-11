---
layout: page
title: Repositories
---

{% for repo in site.data.repos.page %}
- [{{ repo.title }}]({{ repo.url }})
{% endfor %}
