---
layout: page
title: "Encuentros Virtuales"
permalink: /encuentros-virtuales/
---

{% for encuentro in site.data.encuentros %}

<div class="row gtr-50">
    <div class="col-5">
        <span class="image fit"><img src="{{site.baseurl}}/images/{{encuentro.photo}}" alt="" /></span>
    </div>
    <div class="col-7">
        <h3>{{ encuentro.title }}</h3>
        <em>{{ encuentro.date }}</em>
        <br><br>
        {% unless encuentro.description  == empty %}
        <p>{{ encuentro.description }}</p>
        {% endunless %}
        {% if encuentro.initiatives%}
            <h4>Iniciativas:</h4>
            <ul>
            {% for initiative in encuentro.initiatives %}
                <li><h5><a href="{{initiative.url}}">{{initiative.title}}</a> ({{initiative.country}})</h5>
                {% for contact in initiative.contacts %}
                    <em>{{contact.name}}</em>
                    <p>{{contact.info}}</p>
                {% endfor %}  
                </li>
            {% endfor %}  
            </ul>
        {% endif %}

        {% if encuentro.moderators %}
            <h4>Moderador:</h4>
        {% endif %}
        {% for moderator in encuentro.moderators %}
            <h5><a href="{{moderator.url}}">{{moderator.title}}</a> ({{moderator.country}})</h5>
            {% for contact in moderator.contacts %}
                <em>{{contact.name}}</em>
                <p>{{contact.info}}</p>
            {% endfor %}
        {% endfor %}
    </div>
    {% if encuentro.video %}
    <div class="col-12">
        {{encuentro.video}}
    </div>
    {% endif %}

</div>
<br>
{% endfor %}
