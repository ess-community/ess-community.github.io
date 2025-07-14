---
layout: post
title:  "Annual Meeting, May 15, 2023"
date:   2023-05-15
hero_image: /img/ess-ciwg-banner.png
hero_height: is-small
categories: highlight
is_series: true
series_title: "Post"
---

Please join us for this year's Hybrid ESS Cyberinfrastructure Working Groups (CIWG) Annual Meeting. You can view the full Agenda on the meeting's [event page](/events/working_group_meeting_2023).

Note the the meeting is scheduled to run from 9:00AM EDT to 5:30PM EDT.

<br><br> **OLDER POSTS**
{% if page.is_series == true %}
{% assign posts = site.posts
   | where: "is_series", true
   | where: "series_title", page.series_title
   | sort: "date"
   | reverse %}
{% assign dm_posts    = "" | split: "" %}
{% assign m_posts     = "" | split: "" %}
{% assign other_posts = "" | split: "" %}

{% for post in posts %}
  {% if post.url != page.url %}
    {% if post.title contains "Data Management" %}
      {% assign dm_posts = dm_posts | push: post %}
    {% elsif post.title contains "Annual Meeting" %}
      {% assign m_posts = m_posts | push: post %}
    {% else %}
      {% assign other_posts = other_posts | push: post %}
    {% endif %}
  {% endif %}
{% endfor %}

**Data Management Posts**
{% if dm_posts.size > 0 %}
  {% for post in dm_posts %}
- [{{ post.title }}]({{ post.url | prepend: site.baseurl }}) — <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%B %-d, %Y" }}</time>
  {% endfor %}
{% else %}
_No “Data Management” or “dm” posts found._
{% endif %}

**Annual Meeting Posts**
{% if m_posts.size > 0 %}
  {% for post in m_posts %}
- [{{ post.title }}]({{ post.url | prepend: site.baseurl }}) — <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%B %-d, %Y" }}</time>
  {% endfor %}
{% else %}
_No “Annual Meeting” posts found._
{% endif %}

**Other Posts**
{% if other_posts.size > 0 %}
  {% for post in other_posts %}
- [{{ post.title }}]({{ post.url | prepend: site.baseurl }}) — <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%B %-d, %Y" }}</time>
  {% endfor %}
{% else %}
_No other posts._
{% endif %}
{% endif %}