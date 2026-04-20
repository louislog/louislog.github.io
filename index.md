---
layout: default
title: "Home"
---

<div class="hero">
  <div class="hero-text">
    <p class="hero-kicker">Hi, I'm</p>
    <h1 class="hero-title">Louis</h1>
    <section class="slogan-showcase" aria-label="站点理念">
      <div class="slogan-showcase-inner">
        <p class="slogan-showcase-text">
          <span class="slogan-line">Think Deep.</span>
          <span class="slogan-separator" aria-hidden="true"></span>
          <span class="slogan-line">Build Simple.</span>
        </p>
      </div>
    </section>
    <p class="hero-subtitle">
      我是一名长期深耕储能与电池智能算法的算法工程师，专注 ML / TinyML / BatteryML 以及锂电池储能系统（BESS）相关算法。
      在这里，你可以了解我的
      <a href="{{ '/about/' | relative_url }}">背景</a>、
      <a href="{{ '/notes/' | relative_url }}">笔记</a>、
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

<div class="sections-grid">
  <section class="section">
    <h2>近期动态</h2>
    <ul class="post-list">
      {% assign recent_updates = site.posts | concat: site.notes | sort: "date" | reverse %}
      {% for item in recent_updates limit: 6 %}
        <li class="post-item">
          <span class="post-date">{{ item.date | date: "%Y-%m-%d" }}</span>
          {% if item.path contains "_notes" %}
            <span class="note-category tag">笔记</span>
          {% else %}
            <span class="note-category tag">文章</span>
          {% endif %}
          <a class="post-title" href="{{ item.url | relative_url }}">{{ item.title }}</a>
        </li>
      {% endfor %}
      {% if recent_updates.size == 0 %}
        <li class="post-item empty">暂时还没有内容。在 <code>_posts/</code> 发布文章或在 <code>_notes/</code> 更新笔记后会自动出现在这里。</li>
      {% endif %}
    </ul>
  </section>

  <section class="section">
    <h2>技能概览</h2>
    <div class="skill-tags">
      <span class="tag">Machine Learning</span>
      <span class="tag">TinyML</span>
      <span class="tag">BatteryML</span>
      <span class="tag">BESS Algorithms</span>
      <span class="tag">Energy Storage BMS</span>
    </div>
  </section>
</div>

