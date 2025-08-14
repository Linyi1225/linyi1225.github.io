---
title: "学术笔记"
layout: single
permalink: /notes/
classes: wide
---

# 📚 学术笔记

这里收录我的数学研究笔记和理论探索，按专题系统化组织。

## 🔢 数值分析系列

{% assign numerical_posts = site.notes | where_exp: "post", "post.path contains 'numerical-analysis'" | sort: 'date' %}
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

{% assign probability_posts = site.notes | where_exp: "post", "post.path contains 'probability-theory'" | sort: 'date' %}
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

{% assign algebra_posts = site.notes | where_exp: "post", "post.path contains 'linear-algebra'" | sort: 'date' %}
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

{% assign other_posts = site.notes | where_exp: "post", "post.path contains 'numerical-analysis' == false and post.path contains 'probability-theory' == false and post.path contains 'linear-algebra' == false" | sort: 'date' | reverse %}
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

---

<style>
.entries-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 1.5rem;
  margin: 1.5rem 0;
}

.entry {
  padding: 1.5rem;
  background: #f8f9fa;
  border-radius: 8px;
  border-left: 4px solid #007bff;
  transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.entry:hover {
  transform: translateY(-2px);
  box-shadow: 0 4px 12px rgba(0,0,0,0.1);
}

.entry h3 {
  margin: 0 0 1rem 0;
  font-size: 1.2rem;
}

.entry h3 a {
  color: #333;
  text-decoration: none;
}

.entry h3 a:hover {
  color: #007bff;
}

.excerpt {
  color: #666;
  line-height: 1.5;
  margin-bottom: 1rem;
  font-size: 0.95rem;
}

.entry-meta {
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
  gap: 0.5rem;
}

.entry-date {
  color: #6c757d;
  font-size: 0.9rem;
}

.entry-tags {
  display: flex;
  gap: 0.3rem;
  flex-wrap: wrap;
}

.tag {
  background: #e9ecef;
  color: #495057;
  padding: 0.2rem 0.5rem;
  border-radius: 12px;
  font-size: 0.8rem;
  font-weight: 500;
}

@media (max-width: 768px) {
  .entries-grid {
    grid-template-columns: 1fr;
  }
  
  .entry-meta {
    flex-direction: column;
    align-items: flex-start;
  }
}
</style>