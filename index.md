---
title: "Upcoming Training Sessions"
layout: default
---

# 📆 Upcoming Training Sessions

Below are your next scheduled training sessions. This list updates automatically.

---

{% assign sorted_trainings = site.pages | where_exp: "p", "p.path contains 'training/'" | sort: "date" %}
{% assign now = 'now' | date: "%s" %}
{% assign found = false %}

{% for post in sorted_trainings %}
  {% assign training_date = post.date | date: "%s" %}
  {% if training_date > now %}
    {% assign found = true %}

---

## 🔹 [{{ post.title }}]({{ post.url }})

🗓️ **Date:** {{ post.date | date: "%A, %B %d, %Y" }}  
🕒 **Time:** {{ post.start_time }} – {{ post.end_time }}  
🎙️ **Trainer:** {{ post.trainer }}  
🎤 **MC:** {{ post.mc }}  
👥 **Audience:** {{ post.audience }}  
🏷️ **Category:** {{ post.category }}

---

  {% endif %}
{% endfor %}

{% unless found %}
_No upcoming trainings found._
{% endunless %}
