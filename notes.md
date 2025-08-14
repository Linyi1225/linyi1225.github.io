---
title: "学术笔记"
layout: single
permalink: /notes/
classes: wide
---

# 📚 学术笔记

这里收录我的数学研究笔记和理论探索，按专题系统化组织。

## 🔢 数值分析系列

{% assign numerical_posts = site.notes %}
{% assign has_numerical = false %}

{% for post in numerical_posts %}
  {% if post.path contains 'numerical-analysis' %}
    {% assign has_numerical = true %}
    {% break %}
  {% endif %}
{% endfor %}

{% if has_numerical %}
{% for post in numerical_posts %}
  {% if post.path contains 'numerical-analysis' %}
### [{{ post.title }}]({{ post.url | relative_url }})
{% if post.excerpt %}
{{ post.excerpt | strip_html | truncate: 120 }}
{% endif %}
{% if post.date %}
**发布时间**: {{ post.date | date: "%Y年%m月%d日" }}
{% endif %}
{% if post.tags and post.tags.size > 0 %}
**标签**: {% for tag in post.tags limit: 5 %}{{ tag }}{% unless forloop.last %}, {% endunless %}{% endfor %}
{% endif %}
---
  {% endif %}
{% endfor %}
{% else %}
<div class="notice--info">
  <h4>数值分析系列</h4>
  <p>从实数理论出发，构建完整的数值分析理论框架</p>
  <ul>
    <li><strong>理论基础</strong>：实数公理、序列理论、完备性</li>
    <li><strong>分析理论</strong>：函数、极限、连续性、导数</li>
    <li><strong>误差理论</strong>：误差分析、收敛性、数值稳定性</li>
    <li><strong>空间理论</strong>：线性空间、内积空间、逼近论</li>
    <li><strong>应用理论</strong>：迭代法、泛函分析、未来发展</li>
  </ul>
  <p><em>正在建设中...</em></p>
</div>
{% endif %}

---

## 📊 概率论系列

{% assign probability_posts = site.notes %}
{% assign has_probability = false %}

{% for post in probability_posts %}
  {% if post.path contains 'probability-theory' %}
    {% assign has_probability = true %}
    {% break %}
  {% endif %}
{% endfor %}

{% if has_probability %}
{% for post in probability_posts %}
  {% if post.path contains 'probability-theory' %}
### [{{ post.title }}]({{ post.url | relative_url }})
{% if post.excerpt %}
{{ post.excerpt | strip_html | truncate: 120 }}
{% endif %}
{% if post.date %}
**发布时间**: {{ post.date | date: "%Y年%m月%d日" }}
{% endif %}
---
  {% endif %}
{% endfor %}
{% else %}
<div class="notice--info">
  <h4>概率论系列</h4>
  <p>概率论的严格数学基础与现代发展</p>
  <ul>
    <li><strong>测度理论基础</strong>：测度空间、可测函数</li>
    <li><strong>概率空间</strong>：概率测度、随机变量</li>
    <li><strong>积分理论</strong>：Lebesgue积分、期望值理论</li>
    <li><strong>极限定理</strong>：大数定律、中心极限定理</li>
    <li><strong>随机过程</strong>：马尔可夫过程、随机分析</li>
  </ul>
  <p><em>计划中...</em></p>
</div>
{% endif %}

---

## 📐 其他数学主题

{% assign other_posts = site.notes %}
{% assign has_other = false %}

{% for post in other_posts %}
  {% unless post.path contains 'numerical-analysis' or post.path contains 'probability-theory' %}
    {% assign has_other = true %}
    {% break %}
  {% endunless %}
{% endfor %}

{% if has_other %}
{% for post in other_posts %}
  {% unless post.path contains 'numerical-analysis' or post.path contains 'probability-theory' %}
### [{{ post.title }}]({{ post.url | relative_url }})
{% if post.excerpt %}
{{ post.excerpt | strip_html | truncate: 120 }}
{% endif %}
{% if post.date %}
**发布时间**: {{ post.date | date: "%Y年%m月%d日" }}
{% endif %}
{% if post.tags and post.tags.size > 0 %}
**标签**: {% for tag in post.tags limit: 5 %}{{ tag }}{% unless forloop.last %}, {% endunless %}{% endfor %}
{% endif %}
---
  {% endunless %}
{% endfor %}
{% else %}
<div class="notice--secondary">
  <h4>更多主题</h4>
  <p>根据研究需要，会不定期添加其他数学主题的内容，可能包括：</p>
  <ul>
    <li><strong>实分析</strong>：测度论、函数空间</li>
    <li><strong>复分析</strong>：解析函数、留数理论</li>
    <li><strong>泛函分析</strong>：Banach空间、算子理论</li>
    <li><strong>微分几何</strong>：流形、微分形式</li>
    <li><strong>代数拓扑</strong>：同调论、同伦论</li>
  </ul>
</div>
{% endif %}

---

## 📖 阅读指南

### 📚 学习建议

- **系统性学习**：建议按系列顺序阅读，每个系列内部有逻辑递进关系
- **理论与实践**：理论分析配有相应的数值实验和代码实现
- **深度思考**：注重概念的深层理解和数学直觉的培养
- **跨模块学习**：不同系列之间存在内在联系，建议交叉阅读

### 🎯 内容特色

- **严谨的数学表述**：遵循现代数学的表达规范
- **从基础到前沿**：从基本概念到研究前沿的完整覆盖
- **跨学科视角**：结合计算科学、工程应用等多重视角
- **模块化设计**：每个理论模块相对独立，便于专题学习

### 🗺️ 学习路径建议

**初学者路径**：
1. 数值分析 → 理论基础 → 分析理论
2. 概率论 → 基础概念 → 测度理论

**进阶路径**：
1. 数值分析 → 空间理论 → 应用理论
2. 概率论 → 随机过程 → 现代发展

**研究者路径**：
- 根据研究方向选择相关模块深入学习
- 关注理论与应用的结合点

### 💬 交流反馈

欢迎通过以下方式进行学术讨论：
- **邮件**：[lin@deep-matrix.org](mailto:lin@deep-matrix.org)
- **GitHub**：提交Issue或Pull Request
- **学术讨论**：指正错误，提出建议，分享心得

期待与您进行深入的数学理论探讨和学术交流！

---

## 📊 统计信息

- **总计文章数**: {{ site.notes.size }} 篇
- **最后更新**: {{ site.time | date: "%Y年%m月%d日" }}

---

*本学术笔记系列致力于提供严谨而深入的数学理论分析，欢迎数学爱好者和研究者共同探讨。*
