---
title: "Upcoming Training Sessions"
layout: default
---

# 📆 Upcoming Training Sessions

Below are your next scheduled training sessions. This list updates automatically.

---

{% assign sorted_trainings = site.training | sort: "date" %}
{% assign now = 'now' | date: "%s" %}
{% assign found = false %}

{% for post in sorted_trainings %}
  {% assign training_date = post.date | date: "%s" %}
  {% if training_date > now %}
    {% assign found = true %}

---

## 🔹 [{{ post.title }}]({{ site.baseurl }}{{ post.url }})

🗓️ **Date:** {{ post.date | date: "%A, %B %d, %Y" }}  
🕒 **Time:** {{ post.start_time }} – {{ post.end_time }}  
🎙️ **Trainer:** {{ post.trainer }}  
🎤 **MC:** {{ post.mc }}  
👥 **Audience:** {{ post.audience }}  
🏷️ **Category:** {{ post.category }}

---

### 🔥 Promo Headline
**{{ post.promo_headline | default: post.title }}**

### 📣 Promo Body
{{ post.promo_body | default: "No promo body available." }}

### 💬 Client SMS
> {{ post.client_sms | default: "No client SMS available." }}

### 💬 Team SMS
> {{ post.team_sms | default: "No team SMS available." }}

### 📡 Social Post
> {{ post.social_post | default: "No social post provided." }}

---

### 🧠 What You'll Learn

{% if post.learning_points %}
{% assign lines = post.learning_points | split: '\n' %}
{% for line in lines %}
- {{ line | remove: '-' | strip }}
{% endfor %}
{% else %}
_No learning points available._
{% endif %}

---

### 📚 Modules

{% assign module_sections = post.content | split: "### " %}
{% for mod in module_sections %}
  {% if mod contains "**Category:**" %}
  #### {{ mod | split: "\n" | first }}
  {{ mod | remove_first: mod | prepend: "### " }}
  {% endif %}
{% endfor %}

---

  {% endif %}
{% endfor %}

{% unless found %}
_No upcoming trainings found._
{% endunless %}
