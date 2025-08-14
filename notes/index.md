---
title: "学术笔记"
layout: single
permalink: /notes/
classes: wide
---

# 📚 学术笔记

这里收录我的数学研究笔记和理论探索，按专题系统化组织。

## 🔢 数值分析系列

{% assign numerical_posts = '' | split: '' %}
{% for post in site.notes %}
  {% if post.path contains 'numerical-analysis' %}
    {% assign numerical_posts = numerical_posts | push: post %}
  {% endif %}
{% endfor %}
{% assign numerical_posts = numerical_posts | sort: 'date' %}

{% if numerical_posts.size > 0 %}

<div class="entries-grid">
{% for post in numerical_posts %}
  <article class="entry">
    <h3><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
    {% if post.excerpt %}
      <p class="excerpt">{{ post.excerpt | strip_html | truncate: 120 }}</p>
    {% endif %}
    <div class="entry-meta">
      {% if post.date %}
        <span class="entry-date">{{ post.date | date: "%Y年%m月%d日" }}</span>
      {% endif %}
      {% if post.tags and post.tags.size > 0 %}
        <div class="entry-tags">
          {% for tag in post.tags limit: 3 %}
            <span class="tag">{{ tag }}</span>
          {% endfor %}
        </div>
      {% endif %}
    </div>
  </article>
{% endfor %}
</div>

{% else %}

<div class="notice--info">
  <h4>数值分析系列</h4>
  <p>从实数理论出发，构建完整的数值分析理论框架</p>
  <p><em>即将开始...</em></p>
</div>

{% endif %}

---

## 📊 概率论系列

{% assign probability_posts = '' | split: '' %}
{% for post in site.notes %}
  {% if post.path contains 'probability-theory' %}
    {% assign probability_posts = probability_posts | push: post %}
  {% endif %}
{% endfor %}
{% assign probability_posts = probability_posts | sort: 'date' %}

{% if probability_posts.size > 0 %}

<div class="entries-grid">
{% for post in probability_posts %}
  <article class="entry">
    <h3><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
    {% if post.excerpt %}
      <p class="excerpt">{{ post.excerpt | strip_html | truncate: 120 }}</p>
    {% endif %}
    <div class="entry-meta">
      {% if post.date %}
        <span class="entry-date">{{ post.date | date: "%Y年%m月%d日" }}</span>
      {% endif %}
      {% if post.tags and post.tags.size > 0 %}
        <div class="entry-tags">
          {% for tag in post.tags limit: 3 %}
            <span class="tag">{{ tag }}</span>
          {% endfor %}
        </div>
      {% endif %}
    </div>
  </article>
{% endfor %}
</div>

{% else %}

<div class="notice--info">
  <h4>概率论系列</h4>
  <p>概率论的严格数学基础与现代发展</p>
  <p><em>计划中...</em></p>
</div>

{% endif %}

---

## 📐 线性代数系列

{% assign algebra_posts = '' | split: '' %}
{% for post in site.notes %}
  {% if post.path contains 'linear-algebra' %}
    {% assign algebra_posts = algebra_posts | push: post %}
  {% endif %}
{% endfor %}
{% assign algebra_posts = algebra_posts | sort: 'date' %}

{% if algebra_posts.size > 0 %}

<div class="entries-grid">
{% for post in algebra_posts %}
  <article class="entry">
    <h3><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
    {% if post.excerpt %}
      <p class="excerpt">{{ post.excerpt | strip_html | truncate: 120 }}</p>
    {% endif %}
    <div class="entry-meta">
      {% if post.date %}
        <span class="entry-date">{{ post.date | date: "%Y年%m月%d日" }}</span>
      {% endif %}
      {% if post.tags and post.tags.size > 0 %}
        <div class="entry-tags">
          {% for tag in post.tags limit: 3 %}
            <span class="tag">{{ tag }}</span>
          {% endfor %}
        </div>
      {% endif %}
    </div>
  </article>
{% endfor %}
</div>

{% else %}

<div class="notice--info">
  <h4>线性代数系列</h4>
  <p>从向量空间理论到矩阵分析的现代观点</p>
  <p><em>未来规划...</em></p>
</div>

{% endif %}

---

## 📝 其他主题

{% assign other_posts = '' | split: '' %}
{% for post in site.notes %}
  {% assign is_numerical = false %}
  {% assign is_probability = false %}
  {% assign is_algebra = false %}
  
  {% if post.path contains 'numerical-analysis' %}
    {% assign is_numerical = true %}
  {% endif %}
  {% if post.path contains 'probability-theory' %}
    {% assign is_probability = true %}
  {% endif %}
  {% if post.path contains 'linear-algebra' %}
    {% assign is_algebra = true %}
  {% endif %}
  
  {% unless is_numerical or is_probability or is_algebra %}
    {% assign other_posts = other_posts | push: post %}
  {% endunless %}
{% endfor %}
{% assign other_posts = other_posts | sort: 'date' | reverse %}

{% if other_posts.size > 0 %}

<div class="entries-grid">
{% for post in other_posts %}
  <article class="entry">
    <h3><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
    {% if post.excerpt %}
      <p class="excerpt">{{ post.excerpt | strip_html | truncate: 120 }}</p>
    {% endif %}
    <div class="entry-meta">
      {% if post.date %}
        <span class="entry-date">{{ post.date | date: "%Y年%m月%d日" }}</span>
      {% endif %}
      {% if post.tags and post.tags.size > 0 %}
        <div class="entry-tags">
          {% for tag in post.tags limit: 3 %}
            <span class="tag">{{ tag }}</span>
          {% endfor %}
        </div>
      {% endif %}
    </div>
  </article>
{% endfor %}
</div>

{% else %}

<div class="notice--secondary">
  <h4>更多主题</h4>
  <p>根据研究需要，会不定期添加其他数学主题的内容</p>
</div>

{% endif %}

---

## 📖 阅读指南

### 📚 学习建议
- **系统性学习**：建议按系列顺序阅读，每个系列内部有逻辑递进关系
- **理论与实践**：理论分析配有相应的数值实验和代码实现
- **深度思考**：注重概念的深层理解和数学直觉的培养

### 🎯 内容特色
- **严谨的数学表述**：遵循现代数学的表达规范
- **从基础到前沿**：从基本概念到研究前沿的完整覆盖
- **跨学科视角**：结合计算科学、工程应用等多重视角

### 💬 交流反馈
欢迎通过邮件或GitHub进行学术讨论，指正错误，提出建议。
