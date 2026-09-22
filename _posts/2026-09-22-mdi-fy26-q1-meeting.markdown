---
layout: post
title:  "MDI FY26 Q4 Quarterly Meeting"
date:   2026-09-17
hero_image: /img/ess-ciwg-banner.png
hero_height: is-small
categories: highlight
is_series: true
series_title: "Post"
---

**Topic:** ESS CIWG Model-Data Integration Webinar: Lessons from NGEE Arctic

The ESS Cyberinfrastructure Model-Data Integration Working Group is hosting a webinar with Ben Sulman, Verity Salmon, and Jitu Kumar from NGEE Arctic. They will share lessons from modeling, field measurements, computational workflows, data integration, and AI/ML applications. The presentations will be followed by an open discussion on common challenges across projects and where shared examples, guidance, or future working-group activities could help.
<br>
**Date:** Thursday, September 17th, 2026<br>
**Time:** 12:00–1:30 p.m. PT / 3:00–4:30 p.m. ET<br><br>
*Contact co-leads [Vanessa or Forrest](/working-groups/integration) if you are not on the DM email list and want to attend.*

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
