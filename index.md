---
title: "Upcoming Training Sessions"
layout: default
---

# 📆 Upcoming Training Sessions

Below are your next scheduled training sessions. Use the **Promo Copy** to invite your team, post in chats, or promote on social. This list updates automatically as new trainings are added.

---

{% assign upcoming = site.pages | where_exp: "item", "item.date > site.time" | sort: "date" %}
{% if upcoming.size > 0 %}
{% for post in upcoming %}
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

{% endfor %}
{% else %}

## 🙅 No upcoming training sessions found.

Stay tuned! New sessions are posted weekly.

{% endif %}
