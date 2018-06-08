---
layout: page
title: Blog Sitemap
permalink: /all_blogs/
---

{% include sitemaphead.html %}

[//]: # (<script type="text/javascript">)
[//]: # (var categories = [];)
[//]: # (</script>)

{% for category in site.categories %}
{% assign first_date = category[1].first.date | date: "%B %-d %Y" %}
{% assign last_date = category[1].last.date | date: "%B %-d" %}

[//]: # (<script type="text/javascript">)
[//]: # (categories.push("{{ category[0] }}") 
[//]: # (</script>)
<div data-category="{{ category[0] }}">
    <h1>{{ category[0] | capitalize }} Week <span style="font-size: 14px; color: gray;">{{ last_date }} - {{ first_date }}</span></h1>


    <ul class="article-list numitems-{{ category[1].size }}">
    {% for post in category[1] %}
        <li class="article-list__item">
            <span class="post-meta">{{ post.date | date: "%B %-d %Y" }}</span>
                <h5>
                  <a class="post-link" href="{{ post.url }}">
                    {{ post.title }}
                  </a>
                </h5>
        </li>
    {% endfor %}
    </ul>
</div>
{% endfor %}