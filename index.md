---
title: "Upcoming Training Sessions"
layout: default
---

# 📆 Upcoming Training Sessions

Below are your next scheduled training sessions. This list updates automatically.

---

{% assign future_trainings = site.training | sort: "date" %}
{% assign found = false %}

{% for post in future_trainings %}
  {% if post.date and post.date > site.time %}
    {% assign found = true %}

## 🔹 [{{ post.title }}]({{ post.url }})
🗓️ **Date:** {{ post.date | date: "%A, %B %d, %Y" }}  
🎙️ **Trainer:** {{ post.trainer }}  
🎤 **MC:** {{ post.mc }}  

> 🔥 {{ post.promo_headline | default: "Stay tuned for more details!" }}

---
  {% endif %}
{% endfor %}

{% unless found %}
_No upcoming trainings found._
{% endunless %}
