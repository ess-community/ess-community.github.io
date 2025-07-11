---
layout: post
title:  "Data Management FY25 Q4 Quarterly Meeting"
date:   2025-07-11
hero_image: /img/ess-ciwg-banner.png
hero_height: is-small
categories: highlight
is_series: true
series_title: "Post"
---

Topic: What is AI-Ready Data?
<br>Date/Time: Thursday, Aug 28, 12-1pm PT/3-4pm ET

Contact co-leads [Terri or Danielle](/working-groups/data-management) if you are not on the DM email list and want to attend.

<br><br> **OLDER POSTS**
{% if page.is_series == true %}
{% assign posts = site.posts | where: "is_series", true | where: "series_title", page.series_title | sort: 'date' | reverse %}

{% for post in posts %}
        {% if post.url != page.url %}
 		<a href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a> Published on <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%B %-d, %Y" }}</time><br>
        {% endif %}
{% endfor %}
{% endif %}