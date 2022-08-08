---
layout: page
permalink: /miscellaneous/
title: miscellaneous
description: a list of my miscellaneous activities.
nav: true
importance: 2
---

<html>

          
<div class="news">
  <h2>news</h2>
  {% if site.news != blank -%} 
  {%- assign news_size = site.news | size -%}
  <div class="table-responsive">
    <table class="table table-sm table-borderless">
    {%- assign news = site.news | reverse -%}
    {% if site.news_limit %}
    {% assign news_limit = 500 %}
    {% else %}
    {% assign news_limit = news_size %}
    {% endif %}
    {% for item in news limit: news_limit %}
      <tr>
        <th scope="row">{{ item.date | date: "%b %-d, %Y" }}</th>
        <td>
          {% if item.inline -%} 
            {{ item.content | remove: '<p>' | remove: '</p>' | emojify }}
          {%- else -%} 
          <a class="news-title" href="{{ item.url | relative_url }}">{{ item.title }}</a>
          {%- endif %} 
        </td>
      </tr>
      {%- endfor %} 
      </table>
  </div>
  {%- else -%} 
    <p>No news so far...</p>
  {%- endif %} 
  <h2>activities</h2>
  <div class="table-responsive">
    <table class="table table-sm table-borderless">
      <tbody>
        <tr>
          <td>reviewer</td>
          <td> CVPR (2022) | ECCV (2020, 2022) | ICCV (2021) | WACV (2021) | AAAI (2021, 2022) | ICLR (2022) | NeurIPS (2022) </td>
        </tr>
	    </tbody>
    </table>
  </div>
</div>
</html>
