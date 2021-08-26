---
layout: default
title: Speakers
permalink: /speakers.html
page_teaser_image: https://conference.techexeter.uk/images/preview_index.jpg
excerpt: Our speakers for the TechExeter / Digital Exeter annual conference on 8th September 2021.
---

{% assign speakersSorted = site.speakers | sort:"timeslot" %}

<article class="post highlighted speakers">

  <h2>Keynote</h2>
  <div class="grid-flex">
  {% for speaker in speakersSorted %}
    {% if speaker.name == "Liz Jessop" %}
      <div class="speaker">
        <a href="{{ speaker.url }}"><img class="circle" src="{{speaker.headshot}}" alt="Headshot of {{ speaker.name }}"/></a>
        <h2><a href="{{ speaker.url }}">{{ speaker.name }}</a></h2>
        <p>{% if speaker.name != speaker.title %}<strong>{{ speaker.title }}</strong>{% endif %} {% if speaker.company %} <br/>  {{ speaker.company }} {% endif %}</p>
      </div>
    {% endif %}
  {% endfor %}
    </div>

  <h2>Speakers</h2>
  <div class="grid-flex">
  {% for speaker in speakersSorted %}
  {% if speaker.name <>"Liz Jessop" and speaker.name <> "Niki Mosier" and speaker.type <> "Track Host" %}
    <div class="speaker">
        {% if speaker.headshot <> "not-supplied-yet" %} 
        <a href="{{ speaker.url }}"><img class="circle" src="{{speaker.headshot}}" alt="Headshot of {{ speaker.name }}"/></a>
        {% endif %}
        <h2><a href="{{ speaker.url }}">{{ speaker.name }}</a></h2>
      <p>{% if speaker.name != speaker.title %}<strong>{{ speaker.title }}</strong>{% endif %} {% if speaker.company %}  <br/>  {{ speaker.company }} {% endif %}</p>
    </div>
  {% endif %}
  {% endfor %}
  </div>
</article>

<div style="text-align:center;"><em>* Lineup is subject to change</em></div>
