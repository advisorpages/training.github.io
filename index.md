---
title: "Upcoming Training Sessions"
layout: default
---

# 📆 Upcoming Training Sessions

Below are your next scheduled training sessions. Use the **Promo Copy** to invite your team, post in chats, or promote on social. This list updates automatically as new trainings are added.

---

{% assign sorted_trainings = site.training | sort: "date" %}
{% assign found = false %}
{% for post in sorted_trainings %}
  {% if post.date and post.date | date: "%s" > "now" | date: "%s" %}
    {% assign found = true %}

## 🔹 [{{ post.title }}]({{ site.baseurl }}{{ post.url }})
🗓️ **Date:** {{ post.date | date: "%A, %B %d, %Y" }}  
🎙️ **Trainer:** {{ post.trainer }}  
🎤 **MC:** {{ post.mc }}  
🧾 **Promo Copy:**

> **{{ post.title }}**  
> 📅 {{ post.date | date: "%A, %B %d" }}  
> 🔥 {{ post.promo_headline | default: "Stay tuned for our upcoming session!" }}  
> 👉 [View Details]({{ site.baseurl }}{{ post.url }})

---

  {% endif %}
{% endfor %}

{% unless found %}
## 🙅 No upcoming training sessions found.
{% endunless %}
