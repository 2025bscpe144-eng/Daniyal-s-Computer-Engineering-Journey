---
layout: page
title: ""
---

I am **Daniyal Nawaz**, a Computer Engineering student at UET Lahore, Faisalabad Campus. This blog is my digital footprint — an honest account of two semesters of learning, struggling, building, and growing as an engineer.

Guided by **[Dr. Bilal Ahmad](https://www.linkedin.com/in/drbilalphd/)** — professor at UET Lahore, researcher in AI, ML, and Deep Learning.

---

{% assign sorted_posts = site.posts | sort: "date" %}
{% for post in sorted_posts %}
### [{{ post.title }}]({{ post.url | prepend: site.baseurl }})
*{{ post.date | date: "%B %d, %Y" }}*

---
{% endfor %}
