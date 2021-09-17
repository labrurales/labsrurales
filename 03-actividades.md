---
layout: page
title: "Actividades"
permalink: /actividades/
---

<div class="row">

{%for post in site.posts %}

<article class="col-4 col-12-mobile special">
    <a href="{{site.baseurl}}{{post.url}}" class="image featured"><img src="{{site.baseurl}}/images/{{post.image}}"
            alt="{{post.title}}" /></a>
    <header>
        <h3><a href="{{site.baseurl}}{{post.url}}">{{post.title}}</a></h3>
    </header>
    <p>
        {{ post.excerpt | strip_html | truncatewords: 50 }}
    </p>
</article>
{% endfor %}
</div>
