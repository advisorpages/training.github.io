{% assign sorted_trainings = site.training | sort: "date" %}
{% assign found = false %}
{% for post in sorted_trainings %}
  {% if post.date and post.date | date: "%s" > "now" | date: "%s" %}
    {% assign found = true %}

## 🔹 [{{ post.title }}]({{ post.url }})
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
