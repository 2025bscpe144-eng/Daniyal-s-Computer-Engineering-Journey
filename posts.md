---
layout: page
title: Posts
permalink: /posts/
---

All posts from my two semesters at UET Lahore, Faisalabad Campus — documented honestly, week by week.

---

{% for post in site.posts reversed %}
### [{{ post.title }}]({{ post.url | prepend: site.baseurl }})
*{{ post.date | date: "%B %d, %Y" }}*

---
{% endfor %}
