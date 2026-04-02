---
title: "笔记库"
description: "统计物理与复杂系统笔记、推导及讨论"
date: 2024-05-28
tags:
  - 统计物理
  - 复杂系统
  - 玻璃态
  - 阻塞现象
  - 平均场理论
  - 高维物理
---

<style>
/* ================================================
   1. 强制隐藏 Quartz 的所有自动生成标题和页眉
   ================================================ */
.quartz .page-header,
.quartz .article-header,
.page-header,
.article-header,
header,
header + h1,
h1.page-title,
h1.article-title,
h1[data-page-title],
article > header,
article > header > h1,
article > header:first-child,
.quartz .page-title,
.page-title,
.article-title,
.quartz .article .page-header,
.quartz .article header,
.quartz header[role="banner"],
header[role="banner"],
.article-meta,
.page-meta,
.article-date,
.article-time,
.reading-time,
.post-meta,
.meta {
  display: none !important;
  visibility: hidden !important;
  height: 0 !important;
  margin: 0 !important;
  padding: 0 !important;
  overflow: hidden !important;
  opacity: 0 !important;
}

/* 确保页面内容从顶部开始 */
.quartz .article,
.quartz main,
article,
main {
  margin-top: 0 !important;
  padding-top: 0 !important;
}

/* ================================================
   2. 自定义标题样式
   ================================================ */
.page-title-custom {
  font-size: 3rem;
  font-weight: 800;
  text-align: center;
  margin: 0 0 1.5rem 0 !important;
  padding-bottom: 1rem;
  border-bottom: 3px solid var(--secondary);
  color: var(--dark);
  font-family: var(--header-font);
}

/* 标签云样式 */
.tag-cloud {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 0.8rem;
  margin: 1rem 0 2rem 0;
  padding: 1rem 0;
  border-bottom: 1px solid var(--lightgray);
}

.tag-cloud span {
  background: var(--light);
  padding: 0.4rem 1rem;
  border-radius: 20px;
  font-size: 0.9rem;
  color: var(--darkgray);
  border: 1px solid var(--lightgray);
  font-weight: 500;
}

/* ================================================
   3. 修复链接样式
   ================================================ */
/* 确保所有链接都正确显示 */
.category-list a,
.quick-links a,
.tag-cloud a,
.stat-box a,
a[data-internal-link],
a.internal-link {
  color: var(--secondary) !important;
  text-decoration: none !important;
  border-bottom: 1px solid transparent;
  transition: all 0.2s ease;
}

.category-list a:hover,
.quick-links a:hover,
.tag-cloud a:hover,
.stat-box a:hover,
a[data-internal-link]:hover,
a.internal-link:hover {
  color: var(--tertiary) !important;
  border-bottom: 1px solid var(--tertiary);
  background-color: rgba(143, 159, 169, 0.1);
}

/* ================================================
   4. 保持原有布局样式
   ================================================ */
.quick-links table {
  width: 100%;
  border-collapse: collapse;
  margin: 2rem 0;
  font-size: 1.1rem;
}

.quick-links th, .quick-links td {
  padding: 1rem;
  border: 1px solid var(--lightgray);
  text-align: left;
}

.quick-links th {
  background-color: var(--light);
  font-weight: 600;
}

.quick-links tr:hover {
  background-color: rgba(143, 159, 169, 0.1);
}

.section-title {
  font-size: 1.8rem;
  font-weight: 600;
  margin: 2.5rem 0 1.5rem 0;
  padding-left: 0.5rem;
  border-left: 4px solid var(--secondary);
}

.category-list {
  list-style: none;
  padding: 0;
  margin: 1rem 0 2rem 0;
}

.category-list li {
  margin: 0.8rem 0;
  padding-left: 1rem;
  border-left: 2px solid transparent;
  transition: all 0.2s ease;
}

.category-list li:hover {
  border-left-color: var(--tertiary);
  padding-left: 1.5rem;
}

.stats-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 1.5rem;
  margin: 1.5rem 0;
}

.stat-box {
  background: var(--light);
  padding: 1.2rem;
  border-radius: 8px;
  border-left: 4px solid var(--tertiary);
}

.goals-list {
  background: rgba(143, 159, 169, 0.05);
  padding: 1.5rem;
  border-radius: 8px;
  margin: 1.5rem 0;
}

.resources-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 1rem;
  margin: 1.5rem 0;
}

.resource-card {
  background: var(--light);
  padding: 1.2rem;
  border-radius: 8px;
  text-align: center;
  border: 1px solid var(--lightgray);
  transition: transform 0.2s ease;
}

.resource-card:hover {
  transform: translateY(-3px);
  border-color: var(--tertiary);
}

.footer-note {
  text-align: center;
  margin-top: 3rem;
  padding-top: 1.5rem;
  border-top: 1px solid var(--lightgray);
  color: var(--darkgray);
  font-size: 0.9rem;
}


</style>



---

## 🌟 快速导航

<div class="quick-links">

| 领域 | 主要内容 | 近期更新 |
|------|----------|----------|
| **热力学** | [基础概念](理论知识/热力学/v1.md)、[热力学基本过程](理论知识/热力学/v1.md)、[第二定律](理论知识/热力学/v1.md)| 📅 昨天 |
| **平衡态统计** | [全同近独立体系](理论知识/平衡态统计物理/全同近独立粒子系统.md)、[系综理论](理论知识/平衡态统计物理/系综.md) | 📅 今天 |
| **非平衡统计** | [朗之万方程](理论知识/非平衡统计物理/V1.md#1-布朗运动和朗之万方程)、[福特普朗克方程](理论知识/非平衡统计物理/V1.md#2-福特-普朗克方程)、[主方程](理论知识/非平衡统计物理/V1.md#3-主方程)、[量子动力学](理论知识/非平衡统计物理/V1.md#6-量子动力学)、[线性响应理论](理论知识/非平衡统计物理/V1.md#7-线性响应理论)、[投影算子](理论知识/非平衡统计物理/V1.md#8-投影算子)| 📅 3天前 |
| **工具手册** | [常用操作](工具手册/常用操作.md)、[终端命令](工具手册/终端命令.md)、[C++基础](工具手册/C++基础.md)、[Typora Markdown](工具手册/Typora_Markdown.md) | 📅 今天 |

</div>

---

## 📂 笔记内容说明

<div class="section-title">热力学</div>
<div class="category-list">
  <p>主要参考自汪志诚《热力学·统计物理》(第六版)的热力学部分。</p>
    <ul>
    <li>热力学入门概念较多，笔记着重于集中介绍这些概念和理清热力学整体研究思路。</li>
    <li>单元系/多元系相变和热动平衡的内容有待补充。</li>
    <li>笔记目前没有事无巨细的推导和面面俱到的理解，仅服务于，学习统计力学需要掌握的宏观概念。</li>
  </ul>
</div>

<div class="section-title"> 平衡态统计物理</div>
<div class="category-list">
  <p>主要参考自汪志诚《热力学·统计物理》(第六版)的平衡态统计力学部分。包含：</p>
    <ul>
    <li>全同近独立粒子系统。主要内容是玻尔兹曼/玻色、费米子系统的微观状态数，分布，热力学量的统计表达式。也有概念扫盲。</li>
    <li>系综。内容是刘维尔定理，微正则系综，正则系综，巨正则系综</li>
    </ul>
  <p>汪志诚书的系综部分个人读下来比较"潦草"，尤其是微正则系综的逻辑有点"混乱"，笔者为了理清思路加了很多个人思考，不免有失偏颇，有想法请一起讨论，共同修改，完善这部分。特别是学习了Pathria； Beale 的《Statistical Mechanics》之后。</p>
  
</div>

<div class="section-title"> 非平衡统计物理</div>
<div class="category-list">
  <p>主要参考自R. Zwanzig 的《NonequilibriumStatistical Mechanics》</p>
    <ul>
    <li>基本流程是照着书上的章节学习。笔记对于非平衡统计物理目前缺乏系统理解，仅限于对各章节进行严谨的公式推导，概念摸索。</li>
    <li>部分小节标题用``标记，这是没有做的。靠后的内容是原书的翻译，这也是笔者还没有学的。系统学过的内容会换成贴切而清晰的中文表述。</li>
  </ul>
</div>

---

## 🔍 按标签浏览

<div class="tag-cloud">
  <a href="/tags/统计物理">统计物理</a>
  <a href="/tags/复杂系统">复杂系统</a>
  <a href="/tags/推导">推导</a>
  <a href="/tags/代码">代码</a>
  <a href="/tags/热力学">热力学</a>
  <a href="/tags/相变">相变</a>
  <a href="/tags/网络科学">网络科学</a>
</div>

---

## 📈 统计信息

<div class="stats-grid">
  <div class="stat-box">
    <strong>总笔记数</strong><br>
    8 篇
  </div>
  <div class="stat-box">
    <strong>最近更新</strong><br>
    [[理论知识/热力学/V3]]<br>
    2024年5月28日
  </div>
  <div class="stat-box">
    <strong>最常访问</strong><br>
    [[系综理论]]
  </div>
  <div class="stat-box">
    <strong>活跃领域</strong><br>
    统计物理、复杂系统
  </div>
</div>

---

## 📌 近期目标

<div class="goals-list">
1. 完成非平衡统计物理的随机热力学部分
2. 添加复杂网络中的相变示例
3. 编写蒙特卡洛模拟的 Python 示例代码
4. 整理玻璃态物理的实验数据
5. 完善高维统计物理的理论框架
</div>

---

## 🔗 相关资源

<div class="resources-grid">
  <div class="resource-card">
    <strong>📖 经典教材</strong><br>
    Statistical Mechanics<br>
    Complex Systems<br>
    Phase Transitions
  </div>
  <div class="resource-card">
    <strong>💻 计算工具</strong><br>
    Python 代码库<br>
    Jupyter Notebooks<br>
    数据可视化工具
  </div>
  <div class="resource-card">
    <strong>📊 数据集</strong><br>
    实验数据<br>
    模拟结果<br>
    基准测试
  </div>
</div>

<div class="footer-note">
🌐 本网站使用 <a href="https://quartz.jzhao.xyz/" target="_blank">Quartz</a> 构建，基于 GitHub Pages 部署<br>
所有内容遵循 <a href="https://creativecommons.org/licenses/by-sa/4.0/" target="_blank">CC BY-SA 4.0</a> 协议
</div>