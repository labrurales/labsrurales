---
layout: page
title: "Textos"
permalink: /textos/
---

<div class="row">

{%for post in site.textos %}

<article class="col-4 col-12-mobile special">
    <a href="{{site.baseurl}}{{post.url}}" class="image featured"><img src="{{site.baseurl}}/images/{{post.image}}"
            alt="{{post.title}}" /></a>
    <header>
        <h3><a href="{{site.baseurl}}{{post.url}}">{{post.title}}</a></h3>
    </header>
    <p>
        {% if post.author_url %}
            <a href="{{post.author_url}}" target="_blank"><i class="fas fa-home"></i></a>
        {% endif %}
        {% if post.author_twitter %}
            <a href="{{post.author_twitter}}" target="_blank"><i class="fab fa-twitter"></i></a>
        {% endif %}
    {{post.author}}
    </p>
    <p>{{ post.excerpt | strip_html | truncatewords: 10 }}</p>
</article>
{% endfor %}
</div>
