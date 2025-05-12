---
layout: default
title: ...
date: ...
permalink: ...
---

# 📆 Upcoming Training Sessions

Below are your next scheduled training sessions. Use the **Promo Copy** to invite your team, post in chats, or promote on social. This list updates automatically as new trainings are added.

---

{% assign sorted_trainings = site.training | sort: "date" %}
{% assign found = false %}
{% for post in sorted_trainings %}
  {% if post.date and post.date > site.time %}
    {% assign found = true %}

## 🔹 [{{ post.title }}]({{ post.url }})
🗓️ **Date:** {{ post.date | date: "%A, %B %d, %Y" }}  
🎙️ **Trainer:** {{ post.trainer }}  
🎤 **MC:** {{ post.mc }}  
🧾 **Promo Copy:**

> **{{ post.title }}**  
> 📅 {{ post.date | date: "%A, %B %d" }}  
> 🔥 {{ post.promo_headline | default: "Stay tuned for our upcoming session!" }}  
> 👉 [View Details]({{ post.url }})

---

  {% endif %}
{% endfor %}

{% unless found %}
## 🙅 No upcoming training sessions found.

Stay tuned! New sessions are posted weekly.
{% endunless %}
