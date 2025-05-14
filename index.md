## 🔹 [{{ post.title }}]({{ post.url | relative_url }})

🗓️ **Date:** {{ post.date | date: "%A, %B %d, %Y" }}  
🕒 **Time:** {{ post.start_time }} – {{ post.end_time }}  
🎙️ **Trainer Lineup:** {{ post.trainer_lineup }}  

{% if post.promo_body %}
**What's This Session About?**  
{{ post.promo_body }}
{% endif %}

{% if post.topics %}
**Topics We'll Cover:**
<ul>
{% for topic in post.topics %}
  <li>{{ topic }}</li>
{% endfor %}
</ul>
{% endif %}

[🔗 View Details]({{ post.url | relative_url }})
