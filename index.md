---
layout: home
title: "Ecliptic Innovations"


## Recent Posts

{% if site.posts.size > 0 %}
  {% for post in site.posts limit:5 %}
    <div class="post-preview">
      <h3><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
      <p class="post-meta">
        {{ post.date | date: "%B %d, %Y" }} • By {{ post.author }}
        {% if post.tags and post.tags.size > 0 %}
          <br>🏷️ Tags: 
          {% for tag in post.tags %}
            <span class="tag">{{ tag }}</span>{% unless forloop.last %}, {% endunless %}
          {% endfor %}
        {% endif %}
      </p>
      <p>{{ post.excerpt | strip_html | truncatewords: 30 }}</p>
      <a href="{{ post.url | relative_url }}" class="read-more">Read more →</a>
    </div>
    {% unless forloop.last %}<hr>{% endunless %}
  {% endfor %}
  
  <div class="all-posts-link">
    <a href="/posts/" class="btn">View All Posts →</a>
  </div>
{% else %}
  <p>No posts yet. Check back soon for space exploration content!</p>
{% endif %}
