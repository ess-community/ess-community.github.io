---
layout: post
title:  "Annual Meeting, April 14, 2025"
date:   2025-04-14
hero_image: /img/ess-ciwg-banner.png
hero_height: is-small
categories: highlight
is_series: true
series_title: "Post"
---

Please join us for this year's Hybrid ESS Cyberinfrastructure Working Groups (CIWG) Annual Meeting. You can view the full Agenda on the meeting's [event page](/events/working_group_meeting_2025).

Note the the meeting is scheduled to run from 9:00AM EDT to 5:30PM EDT.

<br><br> **OLDER POSTS**
{% if page.is_series == true %}
{% assign posts = site.posts | where: "is_series", true | where: "series_title", page.series_title | sort: 'date' | reverse %}

{% for post in posts %}
        {% if post.url != page.url %}
 		<a href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a> Published on <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%B %-d, %Y" }}</time><br>
        {% endif %}
{% endfor %}
{% endif %}