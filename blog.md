---
layout: page
title: "Blog"
description: "Ideas and Writings"
header-img: "img/twitter.jpg"
---


{% for post in site.posts %}

<div class="post-preview">
    <a href="{{ post.url | prepend: site.baseurl }}">
        <h2 class="post-title">            
            {{ post.title }}
        </h2>
        {% if post.subtitle %}
        <h3 class="post-subtitle">
            {{ post.subtitle }}
        </h3>
        {% endif %}
        <div class="post-content-preview">
            {{ post.content | strip_html | truncate:150 }}
        </div>
    </a>
    <p class="post-meta">Posted by {% if post.author %}{{ post.author }}{% else %}{{ site.title }}{% endif %} on {{ post.date | date: "%B %-d, %Y" }}</p>
</div>

<hr>
{% endfor %}

<!-- Pager -->
{% if site.total_pages > 1 %}
<ul class="pager">
    {% if site.previous_page %}
    <li class="previous">
        <a href="{{ site.previous_page_path | prepend: site.baseurl | replace: '//', '/' }}">&larr; Newer Posts</a>
    </li>
    {% endif %}
    {% if site.next_page %}
    <li class="next">
        <a href="{{ site.next_page_path | prepend: site.baseurl | replace: '//', '/' }}">Older Posts &rarr;</a>
    </li>
    {% endif %}
</ul>
{% endif %}