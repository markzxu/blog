---
layout: page
title: Archive
---

<section>
  {% if site.posts[0] %}
    <ul class="archive-list">
    {%for post in site.posts %}
        <li>
          <time class="archive-date">{{ post.date | date: "%b %d, %Y" }}</time>
          <a href="{{ post.url | prepend: site.baseurl | replace: '//', '/' }}">
            {{ post.title }}
          </a>
        </li>
    {% endfor %}
    </ul>
  {% endif %}
</section>