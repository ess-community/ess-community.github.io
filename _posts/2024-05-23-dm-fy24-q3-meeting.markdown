---
layout: post
title:  "Data Management FY24 Q3 Quarterly Meeting"
date:   2024-05-23
hero_image: /img/ess-ciwg-banner.png
hero_height: is-small
categories: highlight
is_series: true
series_title: "Post"
---

**Topic:** Tools for Implementing Reporting Formats<br>
**Date:** Thursday, May 23<br>
**Time:** 12-1pm PT/3-4pm ET<br><br>
*Contact co-leads [Terri or Danielle](/working-groups/data-management) if you are not on the DM email list and want to attend.*


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