---
layout: page
title: "About"
permalink: /about/
---

<center>
<table>
{% for info in site.data.info.info %}
<tr><th> {{ info.name }} </th><th> {{ info.value }} </th></tr>
{% endfor %}
</table>
</center>
