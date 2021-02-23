---
layout: page
title: Courses
permalink: /docs/
---

# Courses Available

Welcome to {{ site.title }} ! Here you will find an overview of the courses available.

<div class="section-index">
    <hr class="panel-line">
    {% for post in site.docs  %}        
    <div class="entry">
    <h5><a href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a></h5>
    <p>{{ post.description }}</p>
    </div>{% endfor %}
</div>
