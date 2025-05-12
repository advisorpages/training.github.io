---
title: "Upcoming Training Sessions"
layout: default
---

# 📆 Upcoming Training Sessions

Below are your next scheduled training sessions. Use the **Promo Copy** to invite your team, post in chats, or promote on social. This list updates automatically as new trainings are added.

---

{% assign sorted_pages = site.pages | sort: "date" %}
{% assign found = false %}
{% for post in sorted_pages %}
  {% if post.path contains "training/" and post.name != "index.md" and post.date and post.date > site.time %}
    {% assign found = true %}

## 🔹 [{{ post.title }}]({{ post.url }})
🗓️ **Date:** {{ post.date | date: "%A, %B %d, %Y" }}  
🎙️ **Trainer:** {{ post.trainer }}  
🎤 **MC:** {{ post.mc }}  
🧾 **Promo Copy:**

> **{{ post.title }}**  
> 📅 {{ post.date | date: "%A, %B %d" }}  
> 🔥 {{ post.promo_headline }}  
> 👉 [View Details]({{ post.url }})

---

  {% endif %}
{% endfor %}

{% unless found %}
## 🙅 No upcoming training sessions found.

Stay tuned! New sessions are posted weekly.
{% endunless %}
