---
title: "Training Debug"
layout: default
---

# 🧪 Training Collection Debug

**Total Items in Collection:** {{ site.training | size }}

{% for post in site.training %}
---

- **Title:** {{ post.title }}
- **URL:** {{ post.url }}
- **Date:** {{ post.date }}
- **Trainer:** {{ post.trainer }}

{% endfor %}
