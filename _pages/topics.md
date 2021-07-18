---
layout: default
title: topics
permalink: /topics.html
excerpt: Our topics for the TechExeter / Digital Exeter annual conference on 8th September 2021.
---

{% assign speakersSorted = site.speakers | sort:"track"  %}

<article class="post highlighted topics">

  <h1>Topics</h1>
  {% for speaker in speakersSorted %}
  {% if speaker.co-presenting == nil or speaker.co-presenting-primary == 1 %}
    <div>
      <h2><a href="{{ speaker.url }}">{{ speaker.session-title }}</a></h2>
      <h3>{% if speaker.track == "1" %}
      MAIN STAGE
      {% endif %}
      {% if speaker.track == "2" %}
      TECH TRACK
      {% endif %}
      {% if speaker.track == "3" %}
      DIGITAL TRACK
      {% endif %}</h3>
      <p><strong>{{ speaker.name }}</strong>, {% if speaker.name != speaker.title %}{{ speaker.title }} {% endif %} 
      {% if speaker.co-presenting-primary == 1 %} 
        <br/><strong>{{ speaker.co-presenting[0].name }}</strong>, {{ speaker.co-presenting[0].title }}
      {% endif %}
      <br/>
      {% if speaker.company %} {{ speaker.company }} {% endif %}</p>
    </div>
  {% endif %}
  {% endfor %}
</article>



<article class="post">
  <header>
    <div class="title">
      <p>Not all speakers have provided their full information yet, so this page is not representative of the full conference line-up.</p>
    </div>
  </header>
</article>