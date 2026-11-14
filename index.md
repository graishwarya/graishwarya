---
layout: default
title: Blog
---

<section class="hero">
  <p class="eyebrow">A PERSONAL LEARNING JOURNAL</p>
  <h1>Build. Learn. Grow.</h1>
  <p>Thoughts, experiments, and practical notes on product, technology, and life.</p>
  <a class="button" href="#latest">Explore the latest posts ↓</a>
</section>

<section id="latest">
  <div class="section-heading">
    <h2>Latest writing</h2>
    <span class="muted">Learning in public, one note at a time.</span>
  </div>
  <div class="post-grid">
    {% assign sorted_posts = site.posts | sort: "date" | reverse %}
    {% for post in sorted_posts %}
      <article class="post-card">
        <span class="tag">{{ post.category | default: "Learning" }}</span>
        <h3><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
        <p>{{ post.excerpt | default: post.content | strip_html | truncate: 150 }}</p>
        <div class="post-meta">{{ post.date | date: "%b %-d, %Y" }} · <a href="{{ post.url | relative_url }}">Read article →</a></div>
      </article>
    {% endfor %}
  </div>
</section>
