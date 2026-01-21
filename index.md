---
layout: default
title: "Home"
---

<div class="hero">
  <div class="hero-text">
    <p class="hero-kicker">Hi, I'm</p>
    <h1 class="hero-title">Louis</h1>
    <p class="hero-subtitle">
      一个热爱技术与创作的开发者。这里是我的个人主页，你可以了解我的
      <a href="{{ '/about/' | relative_url }}">背景</a>、
      <a href="{{ '/projects/' | relative_url }}">项目</a> 和
      <a href="{{ '/contact/' | relative_url }}">联系方式</a>。
    </p>
    <div class="hero-actions">
      <a class="btn primary" href="{{ '/projects/' | relative_url }}">查看项目</a>
      <a class="btn ghost" href="{{ '/about/' | relative_url }}">关于我</a>
    </div>
  </div>
  <div class="hero-avatar">
    <div class="avatar-circle">
      <span class="avatar-initial">L</span>
    </div>
  </div>
</div>

<section class="section">
  <h2>近期动态</h2>
  <ul class="post-list">
    {% for post in site.posts limit:3 %}
      <li class="post-item">
        <span class="post-date">{{ post.date | date: "%Y-%m-%d" }}</span>
        <a class="post-title" href="{{ post.url | relative_url }}">{{ post.title }}</a>
      </li>
    {% endfor %}
    {% if site.posts == empty %}
      <li class="post-item empty">暂时还没有文章，敬请期待。</li>
    {% endif %}
  </ul>
</section>

<section class="section">
  <h2>技能概览</h2>
  <div class="skill-tags">
    <span class="tag">Frontend</span>
    <span class="tag">Backend</span>
    <span class="tag">DevOps</span>
    <span class="tag">云服务</span>
    <span class="tag">开源贡献</span>
  </div>
</section>

