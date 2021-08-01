---
layout: default
title: Schedule
permalink: /schedule.html
page_teaser_image: https://conference.techexeter.uk/images/preview_index.jpg
excerpt: Schedule for the TechExeter / Digital Exeter annual conference on 8th September 2021.
---

{% assign scheduleSorted = site.speakers | concat: site.data.schedule | sort:"track" | sort:"timeslot" %}

<style type="text/css">

  .schedule-wrap {
      margin:0em 0em 2em;
      border-color: #00bfb2;
      border-width: 1em;
      border-style: solid; 
      background-color:#fff;
  }
  .schedule-wrap h1 {
    font-size: 2rem;
    background-color: #fff;
    padding: 0.5em 0.25em;
    margin:0px;
  }
  #schedule {
    padding:0.25em;
    display: grid;
    grid-gap: 0.2em;
    gap:0.2em;
    grid-template-areas:
      "t-1000 t123-1000 t123-1000 t123-1000"
      "thead t1head t2head t3head"
      "t-1015 t123-1015 t123-1015 t123-1015"
      "t-1030 t1-1030 t2-1030 t3-1030"
      "t-1045 t1-1030 t2-1045 t3-1045"
      "t-1100 t1-1030 t123-1100 t123-1100"
      "t-1115 t1-1115 t2-1115 t3-1115"
      "t-1130 t1-1130 t2-1115 t3-1115"
      "t-1145 t1-1130 t2-1115 t3-1115"
      "t-1200 t123-1200 t123-1200 t123-1200"
      "t-1215 t1-1215 t2-1215 t3-1215"
      "t-1230 t1-1215 t2-1215 t3-1215"
      "t-1245 t1-1245 t2-1215 t3-1215"
      "t-1300 t1-1300 t2-1300 t3-1300"
      "t-1315 t1-1300 t2-1300 t3-1300"
      "t-1330 t1-1300 t2-1300 t3-1300"
      "t-1345 t123-1345 t123-1345 t123-1345"
      "t-1400 t123-1345 t123-1345 t123-1345"
      "t-1415 t123-1345 t123-1345 t123-1345"
      "t-1430 t1-1430 t2-1430 t3-1430"
      "t-1445 t1-1430 t2-1430 t3-1430"
      "t-1500 t1-1430 t2-1430 t3-1430"
      "t-1515 t1-1515 t2-1515 t3-1515"
      "t-1530 t1-1530 t2-1530 t3-1515"
      "t-1545 t1-1530 t2-1530 t123-1515"
      "t-1600 t1-1600 t2-1600 t3-1600"
      "t-1615 t1-1600 t2-1600 t3-1600"
      "t-1630 t123-1630 t123-1630 t123-1630"
      "t-1645 t123-1645 t123-1645 t123-1645"
      ". t1-tba t2-tba t3-tba";
  }
  
  #schedule .small-time {
    display:none;
  }

  @media screen and (max-width: 40em) {
      .schedule-wrap {
        border:0px;
      }
      #schedule {

        box-shadow:none;
        padding:0px;

        grid-gap: 0px;
        gap:0px;
      }
      #schedule .time {
        display:none;
      }

      #schedule .small-time {
        display:inline-block;
      }
  }

</style>

<div class="container">
<div style="text-align:center;">Times below are London, UK. BST (UTC +0100)</div>

<div class="schedule-wrap">
<h1 id="weds">Wednesday 8th September</h1>
<div id="schedule">

  {% for speaker in scheduleSorted %}
  {% if speaker.schedule-ignore == true %}
  {% else %}
    <div class="item {{ speaker.type }} t{{ speaker.track }}" style="grid-area: t{{ speaker.track }}-{{ speaker.timeslot | replace: ".", ""  | replace: ":", "" }};" {% if speaker.type == "time" %} id="time_{{ speaker.timeslot | replace: ".", ""  | replace: ":", "" }}" {% endif %}>
      <div class="small-time">{{ speaker.timeslot }} </div>
      {% if speaker.url %}
      <a href="{{ speaker.url }}">
      {% endif %}
      <h2>{{ speaker.session-title }}</h2>
      {% if speaker.url %}
      </a>
      {% endif %}
      <div class="description">{{ speaker.description }}</div>
      {% if speaker.type != "time" and speaker.type != "break" and speaker.type != "lunch"  and speaker.type != "talk" %}
      <div class="type"> {{ speaker.type }}</div>
      {% endif %}
      <div class="speaker">    
        {% if speaker.names != nil %}
        {{ speaker.names }}
        {% else %}
        {{ speaker.name }}
        {% endif %}
      </div>
    </div>
  {% endif %}
  {% endfor %}

  <div class="item head t1" style="grid-area: t1head;" id="track_1">
  <h2>Track 1</h2>
  MAIN STAGE
  </div>
  <div class="item head t2" style="grid-area: t2head;" id="track_2">
  <h2>Track 2</h2>
  TECH SESSIONS AREA
  </div>
  <div class="item head t3" style="grid-area: t3head;" id="track_3">
  <h2>Track 3</h2>
  DIGITAL SESSIONS AREA
  </div>

</div>
</div>

<div style="text-align:center;"><em>* Schedule is subject to change</em></div>

</div>