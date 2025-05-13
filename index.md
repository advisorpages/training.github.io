---
title: "Upcoming Training Sessions"
layout: default
---

# 📆 Upcoming Training Sessions

Below are your next scheduled training sessions.

---

{% assign sorted_trainings = site.training | sort: "date" %}
{% assign found = false %}

{% for post in sorted_trainings %}
  {% assign training_date = post.date | date: "%s" %}
  {% assign now = site.time | date: "%s" %}
  {% if training_date > now %}
    {% assign found = true %}

## 🔹 [{{ post.title }}]({{ post.url }})
🗓️ **Date:** {{ post.date | date: "%A, %B %d, %Y" }}  
🎙️ **Trainer:** {{ post.trainer }}  
🎤 **MC:** {{ post.mc }}  

> 🔥 {{ post.promo_headline | default: "Promo copy coming soon..." }}

---
  {% endif %}
{% endfor %}

{% unless found %}
_No upcoming trainings found._
{% endunless %}

