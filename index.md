## 🔹 [{{ post.title }}]({{ post.url | relative_url }})

🗓️ **Date:** {{ post.date | date: "%A, %B %d, %Y" }}  
🕒 **Time:** {{ post.start_time }} – {{ post.end_time }}  
🎙️ **Trainer Lineup:** {{ post.data.trainer_lineup }}

{% if post.data.promo_body %}
**What's This Session About?**  
{{ post.data.promo_body }}
{% endif %}

{% if post.data.topics and post.data.topics.size > 0 %}
**Topics We'll Cover:**
<ul>
  {% for topic in post.data.topics %}
    <li>{{ topic }}</li>
  {% endfor %}
</ul>
{% endif %}

[🔗 View Details]({{ post.url | relative_url }})
