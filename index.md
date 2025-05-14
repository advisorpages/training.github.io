---
title: "Upcoming Training & Events"
layout: default
---

# 📆 What's Coming Up?

Stay plugged in. Here’s what’s coming up to help you level up your skills, grow your client base, and build your agency with confidence.

---

{% assign sorted_trainings = site.pages | where_exp: "p", "p.path contains 'training/'" | sort: "date" %}
{% assign now = 'now' | date: "%s" %}
{% assign found = false %}

{% for post in sorted_trainings %}
  {% assign training_date = post.date | date: "%s" %}
  {% if training_date > now %}
    {% assign found = true %}

---

## 🔹 [{{ post.title }}]({{ post.url | relative_url }})

{% if post.promo_body %}
**What's This Session About?**  
{{ post.promo_body }}
{% endif %}

🗓️ **Date:** {{ post.date | date: "%A, %B %d, %Y" }}  
🕒 **Time:** {{ post.start_time }} – {{ post.end_time }}  
🎙️ **Trainer Lineup:** {{ post.trainer_lineup | default: post.trainer }}  

{% assign lines = post.content | newline_to_br | split: "<br />" %}
{% assign topics = lines | where_exp: "line", "line contains '**Topics:**'" %}

{% if topics.size > 0 %}
**Topics We'll Cover:**
<ul>
{% for line in lines %}
  {% if line contains '- ' %}
    <li>{{ line | remove_first: '- ' }}</li>
  {% endif %}
{% endfor %}
</ul>
{% endif %}

[🔗 View Details]({{ post.url | relative_url }})

  {% endif %}
{% endfor %}

{% unless found %}
_No upcoming trainings or events found._
{% endunless %}
