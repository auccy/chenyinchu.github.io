---
title: "About"
layout: gridlay
sitemap: false
permalink: /about/
---

## About Me

{% for member in site.data.pi %}

<div class="jumbotron">
<div class="row">
<div class="col-sm-4">
  <img src="{{ site.url }}{{ site.baseurl }}/images/{{ member.photo }}" width="100%" style="max-width:250px"/>
</div>
<div class="col-sm-8 col-xs-12">
  <h3>{{ member.name }}</h3>
  <h4><i>{{ member.info }}</i></h4>
  {% if member.email %}<a href="mailto:{{ member.email }}" target="_blank"><i class="fa fa-envelope-square fa-3x"></i></a> {% endif %}
  {% if member.cv %} <a href="{{ site.url }}{{ site.baseurl }}/{{ member.cv }}" target="_blank"><i class="ai ai-cv-square ai-3x"></i></a> {% endif %}
  {% if member.scholar %} <a href="{{ member.scholar }}" target="_blank"><i class="ai ai-google-scholar-square ai-3x"></i></a> {% endif %}
  {% if member.github %} <a href="{{ member.github }}" target="_blank"><i class="fa fa-github-square fa-3x"></i></a> {% endif %}
  {% if member.linkedin %} <a href="{{ member.linkedin }}" target="_blank" aria-label="LinkedIn"><i class="fa fa-linkedin-square fa-3x"></i></a> {% endif %}

  <ul style="overflow: hidden">
    {% for education in member.education %}
      <li>{{ education | replace: "-","&#8211;" }}</li>
    {% endfor %}
  </ul>

  {% if member.bio %}
  <p>{{ member.bio }}</p>
  {% endif %}

  {% if member.interests %}
  <h4>Research Interests</h4>
  <ul>
    {% for item in member.interests %}
      <li>{{ item }}</li>
    {% endfor %}
  </ul>
  {% endif %}
</div>
</div>
</div>
{% endfor %}

{% if site.data.awards %}
<div class="jumbotron">
  <h3>Selected Awards and Achievements</h3>
  <ul>
    {% for award in site.data.awards %}
      <li>{{ award.name | replace: "-","&#8211;" }}</li>
    {% endfor %}
  </ul>
</div>
{% endif %}

<div class="jumbotron">
  <h3 id="peer-review">Peer-Review Service</h3>
  <p>My peer-review record includes <strong>55 manuscript reviews across 20 journals</strong>, as of November 2026. This total combines 54 manuscript reviews recorded in Springer Nature Snapp certificates and one review for Alzheimer’s &amp; Dementia.</p>
  <p>I contribute peer reviews in medical AI, dementia, neuroscience, and clinical research methods. Selected journals include</p>
  <ul>
    <li><strong>npj Digital Medicine</strong></li>
    <li><strong>Alzheimer’s Research &amp; Therapy</strong></li>
    <li><strong>Artificial Intelligence Review</strong></li>
    <li><strong>Alzheimer’s &amp; Dementia</strong></li>
  </ul>
  <p>I have also reviewed for npj Dementia, Scientific Reports, BMC Medical Informatics and Decision Making, BMC Neurology, BMC Medical Research Methodology, and other journals.</p>
</div>

{% if site.data.people %}
<div class="jumbotron">
  <h3 id="research-collaborations">Research Collaborations</h3>
  <ul>
    {% for collaborator in site.data.people %}
      <li>{% if collaborator.url %}<a href="{{ collaborator.url }}">{{ collaborator.name }}</a>{% else %}{{ collaborator.name }}{% endif %}</li>
    {% endfor %}
  </ul>
</div>
{% endif %}
