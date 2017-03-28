---
title: "Blog Archive"
permalink: /archive/
layout: page
---

  {% capture site_lang %}{{ site.lang | default: "en" }}{% endcapture %}

  <ul class="post-archives">
    {% for post in site.posts %}
      {% capture post_lang %}{{ post.lang | default: site_lang }}{% endcapture %}
      {% capture lang %}{% if post_lang != site_lang %}{{ post_lang }}{% endif %}{% endcapture %}

      <li style="display:none;" class="category-default {% for cat in post.categories %}category-{{cat}} {% endfor %}">
        <span class="post-meta">{{ post.date | date: "%b %-d, %Y" }}{% if post.categories != empty %} • {% include category_links.html categories=post.categories %}{% endif %}</span>

        <h2>
          <a class="post-link" href="{{ post.url | relative_url }}"{% if lang != empty %} lang="{{ lang }}"{% endif %}>{{ post.title | escape }}{% if post.external-url %} &rarr;{% endif %}</a>
        </h2>
      </li>
    {% endfor %}
  </ul>
  <script>
  var q=window.location.search
  var classname
  if(q)
      classname="category-"+q.substring(1)
  else
      classname="category-default"
  for(var e of document.getElementsByClassName(classname))e.style.display=""
  </script>
