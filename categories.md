---
layout: page
title: Categories"
permalink: /categories/
---

{% for post in site.posts %}
  {{ post.title}}, {{post.categories}}
   
   <br/>
       
      
    {% endfor %}
