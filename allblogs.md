---
layout: page
title: Blog Sitemap
permalink: /all_blogs/
---

{% include sitemaphead.html %}

{% for category in site.categories %}
{% assign first_date = category[1].first.date | date: "%B %-d %Y" %}
{% assign last_date = category[1].last.date | date: "%B %-d" %}
<h1>{{ category[0] | capitalize }} Week <span style="font-size: 14px; color: gray;">{{ last_date }} - {{ first_date }}</span></h1>


<table style="border: none;">
    <tr>
    {% for post in category[1] %}
        <td style="border:none;">
            <span class="post-meta">{{ post.date | date: "%B %-d %Y" }}</span>
                <h5>
                  <a class="post-link" href="{{ post.url }}">
                    {{ post.title }}
                  </a>
                </h5>
        </td>
    {% endfor %}
    </tr>
</table>
{% endfor %}