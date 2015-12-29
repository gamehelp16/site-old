---
layout: default
title: Home
---

##Posts

{% for post in site.posts %}
  * [ {{ post.title }} ]({{ post.url }}) <span style="color:#888;">{{ post.date | date_to_string }}</span><br>
{% endfor %}