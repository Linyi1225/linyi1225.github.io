---
title: "学术笔记"
layout: single
permalink: /notes/
classes: wide
---

# 📚 学术笔记

这里收录我的数学研究笔记和理论探索，按专题系统化组织。

## 🔢 数值分析系列

{% comment %}
检查是否有数值分析的主目录文件
{% endcomment %}
{% assign numerical_main = site.notes | where: "path", "_notes/numerical-analysis/index.md" | first %}
{% assign numerical_posts = site.notes | where_exp: "post", "post.path contains 'numerical-analysis'" %}
{% assign numerical_sections = numerical_posts | where_exp: "post", "post.path contains '/index.md'" | sort: "path" %}
{% assign numerical_articles = numerical_posts | where_exp: "post", "post.path contains '/index.md' == false" | sort: "date" %}

{% if numerical_main %}
### 📖 [完整理论体系：从实数公理到数值分析]({{ numerical_main.url | relative_url }})

{{ numerical_main.excerpt | strip_html | truncate: 200 }}

**理论模块**：
{% for section in numerical_sections %}
  {% unless section.path contains 'numerical-analysis/index.md' %}
- [{{ section.title }}]({{ section.url | relative_url }})
  {% endunless %}
{% endfor %}

{% if numerical_main.date %}
**最后更新**: {{ numerical_main.date | date: "%Y年%m月%d日" }}
{% endif %}

---

{% if numerical_articles.size > 0 %}
**最近文章**：
{% for post in numerical_articles limit: 3 %}
- [{{ post.title }}]({{ post.url | relative_url }}) {% if post.date %}({{ post.date | date: "%m月%d日" }}){% endif %}
{% endfor %}
{% if numerical_articles.size > 3 %}
- [查看更多...]({{ numerical_main.url | relative_url }})
{% endif %}
{% endif %}

{% elsif numerical_posts.size > 0 %}
{% comment %}
如果没有主目录文件，显示所有数值分析相关文章
{% endcomment %}
{% for post in numerical_posts %}
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

{% assign probability_main = site.notes | where: "path", "_notes/probability-theory/index.md" | first %}
{% assign probability_posts = site.notes | where_exp: "post", "post.path contains 'probability-theory'" %}
{% assign probability_sections = probability_posts | where_exp: "post", "post.path contains '/index.md'" | sort: "path" %}
{% assign probability_articles = probability_posts | where_exp: "post", "post.path contains '/index.md' == false" | sort: "date" %}

{% if probability_main %}
### 📈 [概率论的现代理论基础]({{ probability_main.url | relative_url }})

{{ probability_main.excerpt | strip_html | truncate: 200 }}

{% if probability_sections.size > 1 %}
**理论模块**：
{% for section in probability_sections %}
  {% unless section.path contains 'probability-theory/index.md' %}
- [{{ section.title }}]({{ section.url | relative_url }})
  {% endunless %}
{% endfor %}
{% endif %}

{% elsif probability_posts.size > 0 %}
{% for post in probability_posts %}
### [{{ post.title }}]({{ post.url | relative_url }})
{% if post.excerpt %}
{{ post.excerpt | strip_html | truncate: 120 }}
{% endif %}
{% if post.date %}
**发布时间**: {{ post.date | date: "%Y年%m月%d日" }}
{% endif %}
---
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

{% assign other_posts = '' | split: '' %}
{% for post in site.notes %}
  {% assign is_numerical = false %}
  {% assign is_probability = false %}
  
  {% if post.path contains 'numerical-analysis' %}
    {% assign is_numerical = true %}
  {% endif %}
  {% if post.path contains 'probability-theory' %}
    {% assign is_probability = true %}
  {% endif %}
  
  {% unless is_numerical or is_probability %}
    {% assign other_posts = other_posts | push: post %}
  {% endunless %}
{% endfor %}
{% assign other_posts = other_posts | sort: 'date' | reverse %}

{% if other_posts.size > 0 %}
{% for post in other_posts %}
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

---
title: "学术笔记"
layout: single
permalink: /notes/
classes: wide
---

# 📚 学术笔记

这里收录我的数学研究笔记和理论探索，按专题系统化组织。

## 🔢 数值分析系列

{% comment %}
检查是否有数值分析的主目录文件
{% endcomment %}
{% assign numerical_main = site.notes | where: "path", "_notes/numerical-analysis/index.md" | first %}
{% assign numerical_posts = site.notes | where_exp: "post", "post.path contains 'numerical-analysis'" %}
{% assign numerical_sections = numerical_posts | where_exp: "post", "post.path contains '/index.md'" | sort: "path" %}
{% assign numerical_articles = numerical_posts | where_exp: "post", "post.path contains '/index.md' == false" | sort: "date" %}

{% if numerical_main %}
### 📖 [完整理论体系：从实数公理到数值分析]({{ numerical_main.url | relative_url }})

{{ numerical_main.excerpt | strip_html | truncate: 200 }}

**理论模块**：
{% for section in numerical_sections %}
  {% unless section.path contains 'numerical-analysis/index.md' %}
- [{{ section.title }}]({{ section.url | relative_url }})
  {% endunless %}
{% endfor %}

{% if numerical_main.date %}
**最后更新**: {{ numerical_main.date | date: "%Y年%m月%d日" }}
{% endif %}

---

{% if numerical_articles.size > 0 %}
**最近文章**：
{% for post in numerical_articles limit: 3 %}
- [{{ post.title }}]({{ post.url | relative_url }}) {% if post.date %}({{ post.date | date: "%m月%d日" }}){% endif %}
{% endfor %}
{% if numerical_articles.size > 3 %}
- [查看更多...]({{ numerical_main.url | relative_url }})
{% endif %}
{% endif %}

{% elsif numerical_posts.size > 0 %}
{% comment %}
如果没有主目录文件，显示所有数值分析相关文章
{% endcomment %}
{% for post in numerical_posts %}
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

{% assign probability_main = site.notes | where: "path", "_notes/probability-theory/index.md" | first %}
{% assign probability_posts = site.notes | where_exp: "post", "post.path contains 'probability-theory'" %}
{% assign probability_sections = probability_posts | where_exp: "post", "post.path contains '/index.md'" | sort: "path" %}
{% assign probability_articles = probability_posts | where_exp: "post", "post.path contains '/index.md' == false" | sort: "date" %}

{% if probability_main %}
### 📈 [概率论的现代理论基础]({{ probability_main.url | relative_url }})

{{ probability_main.excerpt | strip_html | truncate: 200 }}

{% if probability_sections.size > 1 %}
**理论模块**：
{% for section in probability_sections %}
  {% unless section.path contains 'probability-theory/index.md' %}
- [{{ section.title }}]({{ section.url | relative_url }})
  {% endunless %}
{% endfor %}
{% endif %}

{% elsif probability_posts.size > 0 %}
{% for post in probability_posts %}
### [{{ post.title }}]({{ post.url | relative_url }})
{% if post.excerpt %}
{{ post.excerpt | strip_html | truncate: 120 }}
{% endif %}
{% if post.date %}
**发布时间**: {{ post.date | date: "%Y年%m月%d日" }}
{% endif %}
---
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

{% assign other_posts = '' | split: '' %}
{% for post in site.notes %}
  {% assign is_numerical = false %}
  {% assign is_probability = false %}
  
  {% if post.path contains 'numerical-analysis' %}
    {% assign is_numerical = true %}
  {% endif %}
  {% if post.path contains 'probability-theory' %}
    {% assign is_probability = true %}
  {% endif %}
  
  {% unless is_numerical or is_probability %}
    {% assign other_posts = other_posts | push: post %}
  {% endunless %}
{% endfor %}
{% assign other_posts = other_posts | sort: 'date' | reverse %}

{% if other_posts.size > 0 %}
{% for post in other_posts %}
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

{% assign total_posts = site.notes.size %}
{% assign numerical_count = numerical_posts.size %}
{% assign probability_count = probability_posts.size %}
{% assign other_count = other_posts.size %}

- **总计文章数**: {{ total_posts }} 篇
- **数值分析系列**: {{ numerical_count }} 篇
- **概率论系列**: {{ probability_count }} 篇  
- **其他主题**: {{ other_count }} 篇
- **最后更新**: {{ site.time | date: "%Y年%m月%d日" }}

{% comment %}
显示最近更新的文章
{% endcomment %}
{% assign recent_posts = site.notes | sort: 'date' | reverse | limit: 3 %}
{% if recent_posts.size > 0 %}
**最近更新**:
{% for post in recent_posts %}
- [{{ post.title }}]({{ post.url | relative_url }}) ({{ post.date | date: "%m月%d日" }})
{% endfor %}
{% endif %}

---

*本学术笔记系列致力于提供严谨而深入的数学理论分析，欢迎数学爱好者和研究者共同探讨。*
