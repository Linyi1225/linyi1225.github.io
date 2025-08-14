---
title: "学术笔记"
layout: single
permalink: /notes/
classes: wide
---

## 📚 学术笔记集合

{% if site.notes and site.notes.size > 0 %}

<div class="grid">
{% for note in site.notes %}
  <div class="grid__item">
    <article class="archive__item" itemscope itemtype="https://schema.org/CreativeWork">
      <h2 class="archive__item-title" itemprop="headline">
        <a href="{{ note.url | relative_url }}" rel="permalink">{{ note.title }}</a>
      </h2>
      
      {% if note.excerpt %}
        <p class="archive__item-excerpt" itemprop="description">{{ note.excerpt | markdownify | strip_html | truncate: 160 }}</p>
      {% endif %}
      
      {% if note.date %}
        <p class="page__date"><strong><i class="fas fa-fw fa-calendar-alt" aria-hidden="true"></i> 日期：</strong> <time datetime="{{ note.date | date_to_xmlschema }}">{{ note.date | date: "%B %d, %Y" }}</time></p>
      {% endif %}
      
      {% if note.tags and note.tags.size > 0 %}
        <p class="page__meta">
          <strong><i class="fas fa-fw fa-tags" aria-hidden="true"></i> 标签：</strong>
          {% for tag in note.tags %}
            <span class="page__taxonomy-item" rel="tag">{{ tag }}</span>{% unless forloop.last %}, {% endunless %}
          {% endfor %}
        </p>
      {% endif %}
    </article>
  </div>
{% endfor %}
</div>

{% else %}

<div class="notice--info">
  <h4>暂无内容</h4>
  <p>学术笔记正在整理中，敬请期待更多精彩内容...</p>
</div>

{% endif %}

---

## 🔬 研究领域

本站的学术笔记主要涵盖以下领域：

**理论数学**
- 代数结构与抽象代数
- 数学分析与实变函数
- 几何学与拓扑学
- 数论与组合数学

**应用数学**
- 计算数学与数值方法
- 优化理论与算法设计
- 概率统计与随机过程
- 数学建模与仿真

**交叉学科**
- 计算机科学中的数学
- 物理学中的数学方法
- 工程数学应用
- 数据科学与机器学习

---

## 📖 阅读指南

- **基础理论**：适合数学专业学生和研究者
- **应用实例**：包含具体的计算和代码实现
- **个人思考**：记录学习过程中的心得体会
- **参考文献**：提供进一步学习的资源

每篇笔记都经过仔细整理，希望能为同行学者提供有价值的参考。
