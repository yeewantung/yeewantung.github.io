---
layout: page
title: "About"
permalink: /about/
---

Hello, I am Hao Zhang, an undergraduate student from USTC, majoring in CMP.

<center>
<table>
<caption><h4>Social software I prefer</h4></caption>
{% for info in site.data.info.info %}
<tr><th> {{ info.name }} </th><th> {{ info.value }} </th></tr>
{% endfor %}
</table>
</center>
