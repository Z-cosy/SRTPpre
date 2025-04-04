---
theme: seriph
aspectRatio: '16/9'
layout: image-right
image: './images/cover.png'  # 注意这里使用相对路径
---

<style>
.blue-bold {
  color:rgb(5, 81, 156);
  font-weight: bold;
}
/* 这会应用于除第一页外的所有幻灯片 */
.slidev-layout:not(.slidev-page-1 .slidev-layout)::before {
  content: '';
  position: fixed;
  top: 10px;
  right: 10px;
  width: 140px;
  height: 60px;
  background-image: url('./images/ee.png'), url('./images/zju.png');
  background-position: right top, right 70px top;
  background-repeat: no-repeat;
  background-size: 60px auto;
  z-index: 100;
  pointer-events: none;
}

/* 首页左上角图标样式 */
.slidev-page-1 .slidev-layout::before {
  content: '';
  position: fixed;
  top: 10px;
  left: 10px;
  width: 140px;
  height: 60px;
  background-image: url('./images/ee.png'), url('./images/zju.png');
  background-position: left top, left 70px top;
  background-repeat: no-repeat;
  background-size: 60px auto;
  z-index: 100;
  pointer-events: none;
}

/* 目录样式 */
.custom-toc {
  width: 80%;
  margin: 40px auto;
  font-size: 1.3em;
  line-height: 1.8;
}

.toc-item {
  margin-bottom: 0.5em;
  display: flex;
}

.toc-number {
  width: 30px;
  text-align: right;
  margin-right: 10px;
}

.sub-toc-item {
  margin-left: 40px;
  display: flex;
}

.sub-toc-number {
  width: 30px;
  text-align: right;
  margin-right: 10px;
}

/* 高亮和暗化样式 */
.dimmed {
  opacity: 0.3;
}

.highlighted {
  color: #000000; /* 改为黑色 */
  font-weight: bold;
}

/* 首页特殊样式 */
.cover-content {
  display: flex;
  flex-direction: column;
  justify-content: center;
  height: 100%;
  padding: 0 1rem;
}

.cover-content h1 {
  font-size: 2.2rem;
  line-height: 1.3;
  margin-bottom: 1.5rem;
  font-weight: bold;
}

.cover-content .subtitle {
  font-size: 1.5rem;
  margin-top: 1.5rem;
  color: #555;
}

.cover-content .logos {
  margin-top: 3rem;
  display: flex;
  align-items: center;
}

.cover-content .logos img {
  height: 3rem;
  margin-right: 1.5rem;
}
</style>

<div class="cover-content">
  <h1>具备电网故障穿越能力的双馈风力发电机无位置传感器控制技术研究</h1>
  <div class="subtitle">答辩人：曾文博</div>
  <div class="subtitle">指导老师：王涛</div>
</div>

---
 
# 目录

<div class="custom-toc">
  <div class="toc-item"><span class="toc-number">1.</span> 研究初衷与研究现状 <span style="color: #666; font-size: 0.85em;">Research Motivation & Current Status</span></div>
  <div class="toc-item"><span class="toc-number">2.</span> 前期工作与前期成果 <span style="color: #666; font-size: 0.85em;">Preliminary Work & Achievements</span></div>
  <div class="toc-item"><span class="toc-number">3.</span> 关键问题与未来工作 <span style="color: #666; font-size: 0.85em;">Key Issues & Future Work</span></div>
  <div class="toc-item"><span class="toc-number">4.</span> 申请人简历 <span style="color: #666; font-size: 0.85em;">Applicant's Resume</span></div>
</div>


---
  
# 目录

<div class="custom-toc">
  <div class="toc-item highlighted"><span class="toc-number">1.</span> 研究初衷与研究现状 <span style="color: #666; font-size: 0.85em;">Research Motivation & Current Status</span></div>
  <div class="toc-item dimmed"><span class="toc-number">2.</span> 前期工作与前期成果 <span style="color: #666; font-size: 0.85em;">Preliminary Work & Achievements</span></div>
  <div class="toc-item dimmed"><span class="toc-number">3.</span> 关键问题与未来工作 <span style="color: #666; font-size: 0.85em;">Key Issues & Future Work</span></div>
  <div class="toc-item dimmed"><span class="toc-number">4.</span> 申请人简历 <span style="color: #666; font-size: 0.85em;">Applicant's Resume</span></div>
</div>

---
layout: image-right
image: '/images/windturbine.png'  # 替换为您的图片路径
---

# 研究初衷与研究现状

## 研究初衷
- **风力发电**是应对全球能源问题的重要手段
- **海上风电**确定为可再生能源发展的重点领域
- 世界主流的风力发电机可分为**永磁同步发电机(PMSG)**和**双馈异步发电机(DFIG)**
- **位置传感器**精密的机械结构较易损坏，是风力发电机组的**薄弱环节**
- 这在海上潮湿、盐雾环境下尤为突出，极大增加了海上风电的运维成本
<br><br>

<v-click>
<div class="simple-underline">
  是否有方法可以不依赖位置传感器，通过电机的电磁耦合特性算出转子位置？
</div>
</v-click>

<style>
.simple-underline {
  display: inline-block;
  position: relative;
  font-weight: bold;
  color: #1a56db;
  padding: 10px 0;
}

.simple-underline::after {
  content: '';
  position: absolute;
  width: 0;
  height: 3px;
  bottom: 0;
  left: 0;
  background-color: #1a56db;
  animation: underline-grow 2s forwards;
  animation-delay: 0.5s;
}

@keyframes underline-grow {
  to { width: 100%; }
}
</style>
---
layout: image-right
image: '/images/paper.png'  # 替换为您的图片路径
---

# 研究初衷与研究现状

## 研究现状
- PMSG的无位置传感器控制技术**较为成熟**，已在大多数产品中**批量应用**
- DFIG的无位置传感器技术虽已有一些**学术研究**，但**暂无用于批量产品**的报道
<br><br>
### 其主要原因是：
- 现有DFIG转子位置估计方法通常**仅适用于正常电网条件**
- DFIG定子**与电网直接相连**，电网故障时电机的定子电压、电流将受到直接而剧烈的影响，进而引起**转子位置估计误差**，导致**故障穿越失败**。
---
 
# 目录

<div class="custom-toc">
  <div class="toc-item dimmed"><span class="toc-number">1.</span> 研究初衷与研究现状 <span style="color: #666; font-size: 0.85em;">Research Motivation & Current Status</span></div>
  <div class="toc-item highlighted"><span class="toc-number">2.</span> 前期工作与前期成果 <span style="color: #666; font-size: 0.85em;">Preliminary Work & Achievements</span></div>
  <div class="toc-item dimmed"><span class="toc-number">3.</span> 关键问题与未来工作 <span style="color: #666; font-size: 0.85em;">Key Issues & Future Work</span></div>
  <div class="toc-item dimmed"><span class="toc-number">4.</span> 申请人简历 <span style="color: #666; font-size: 0.85em;">Applicant's Resume</span></div>
</div>

---
layout: image-right
image: '/images/book.png'  # 替换为您的图片路径
---

# 理论基础
- 提前自学了《电机学》《控制论》等课程的相关部分
- 详细研读了多篇DFIG建模、控制相关的基础论文

  → **初步具备了DFIG控制相关理论知识**
- 围绕DFIG无位置传感器控制策略，通过IEEE Xplore等查阅了数十篇国内外文献
- 对现有控制策略进行了总结归纳，并撰写了**文献综述报告**

  → **初步了解了国内外DFIG无位置传感器控制的研究现状**
---
layout: image-right
image: '/images/MRAS.png'  # 替换为您的图片路径
---

# 三类Senosorless方法仿真复现


- 掌握了仿真软件Simulink的使用方法
- 仿真复现了**开环法**、**模型参考自适应法**以及**高频信号注入法**三类无位置传感器控制策略
## 仿真结果
- **开环法**严重依赖电机参数，闭环反馈机制缺失❌
- **高频信号注入法**严重影响发电质量，难以实际应用❌
- **MRAS**在稳态下能够准确跟踪转子位置和转速，转子位置观测角在暂态过程中收敛速度较快，具有低电压穿越的潜力✅

---
layout: image-right
image: '/images/your-image.png'
---

<div class="image-control">
  <div class="image-top">
    <img src="/images/control.png" alt="策略图">
  </div>
  <div class="image-bottom">
    <img src="/images/Zstradegy.png" alt="第二张图片"> <!-- 这里需要替换为第二张图片的路径 -->
  </div>
</div>

# 基于电压前馈的初步成果
设计思路：将电网电压有关的项从闭环中分离出来，作为电压前馈项，从而提高故障穿越能力

- 基于电网电压前馈的思想设计闭环控制+前馈补偿系统
- 仿真结果表明，该方法能够**有效提高DFIG的故障穿越能力**

→

<span style="background-color: lightblue;">**基于该方法的初步成果已整理成文并向专利局递交专利申请**</span>

<style>
/* 隐藏原来的背景图片 */
.slidev-layout.image-right::after {
  display: none;
}

/* 控制新插入的图片容器 */
.image-control {
  position: absolute;
  top: 0;
  right: 0;
  width: 55%;  /* 控制图片区域宽度 */
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  padding: 40px 0px;
}

/* 上方图片容器 */
.image-top {
  width: 100%;
  height: 48%;
}

/* 下方图片容器 */
.image-bottom {
  width: 100%;
  height: 48%;
}

/* 图片样式 */
.image-control img {
  width: 100%;
  height: 100%;
  object-fit: contain;
}
</style>

---
layout: cover
background: /images/patent.png
class: no-logo-slide

---


## 基于该方法的初步成果已<span class="blue-bold">整理定稿</span>

## 并已通过浙江大学科研系统递交<span class="blue-bold">专利申请</span>

<style>
/* 为当前页面去掉右上角的 logo */
.no-logo-slide::before {
  display: none !important;
}
</style>


---
 
# 目录

<div class="custom-toc">
  <div class="toc-item dimmed"><span class="toc-number">1.</span> 研究初衷与研究现状 <span style="color: #666; font-size: 0.85em;">Research Motivation & Current Status</span></div>
  <div class="toc-item dimmed"><span class="toc-number">2.</span> 前期工作与前期成果 <span style="color: #666; font-size: 0.85em;">Preliminary Work & Achievements</span></div>
  <div class="toc-item highlighted"><span class="toc-number">3.</span> 关键问题与未来工作 <span style="color: #666; font-size: 0.85em;">Key Issues & Future Work</span></div>
  <div class="toc-item dimmed"><span class="toc-number">4.</span> 申请人简历 <span style="color: #666; font-size: 0.85em;">Applicant's Resume</span></div>
</div>

---
layout: default
---

<div class="grid-container">
  <div class="grid-item">
    <h3>Q1：现有方法的数学本质</h3>
    <ul>
      <li>现有方法的实现依靠直觉与感性认识</li>
      <li>如何从数学上解释其故障穿越能力？</li>
      <li>结合DFIG故障穿越暂态过程研究，<span class="highlight">定量描述其动态特性</span></li>
    </ul>
  </div>
  
  <div class="grid-item">
    <h3>Q2：电网电压前馈机制优化</h3>
    <ul>
      <li>现有前馈机制根据DFIG数学模型直接给出</li>
      <li>计算复杂，暂态过程不稳定</li>
      <li>对电网电压信息进行<span class="highlight">"预处理"，改进现有前馈机制</span></li>
    </ul>
  </div>
  
  <div class="grid-item">
    <h3>Q3：模型参数的整定</h3>
    <ul>
      <li>模型的关键闭环部分用到了PI控制器</li>
      <li>PI控制器的参数依靠经验与大量实验给出</li>
      <li>优化参数整定，<span class="highlight">给出其最优参数组合策略</span></li>
    </ul>
  </div>
  
  <div class="grid-item">
    <h3>Q4：与灭磁与无功支撑控制耦合</h3>
    <ul>
      <li>目前的仿真中均采用的是最基础的FOC控制</li>
      <li>实际工程中，故障条件下有特定的控制要求</li>
      <li>无位置传感器与上述控制策略<span class="highlight">耦合分析</span></li>
    </ul>
  </div>
</div>

<h1 class="page-title">关键问题</h1>

<style>
.page-title {
  position: absolute;
  top: 10px;
  left: 0;
  width: 100%;
  text-align: center;
  font-size: 2rem;
  margin: 0;
  padding: 10px 0;
}

.grid-container {
  display: grid;
  grid-template-columns: 1fr 1fr;
  grid-template-rows: 1fr 1fr;
  gap: 20px;
  height: 100;
  width: 100%;
  padding: 30px 0px 10px 0px;
  box-sizing: border-box;
}

.grid-item {
  background-color: rgba(240, 240, 240, 0.7);
  border-radius: 10px;
  padding: 20px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  display: flex;
  flex-direction: column;
  overflow: auto;
}

.grid-item h3 {
  margin-top: 0;
  margin-bottom: 15px;
  color: #2c3e50;
  border-bottom: 2px solid #3498db;
  padding-bottom: 8px;
}

.grid-item ul {
  margin: 0;
  padding-left: 20px;
}

.grid-item li {
  margin-bottom: 8px;
}

.highlight {
  background-color: rgba(135, 206, 250, 0.7); /* 浅蓝色背景 */
  padding: 0 3px;
  font-weight: bold;
  border-radius: 3px;
}
</style>

---
layout: two-cols
title: 未来工作规划
---
<style>
.slidev-layout {
  padding-top: 2rem;
}
.mermaid {
  margin-top: -10px; /* 负边距使图表上移 */
}
</style>

<template v-slot:default>

<div class="mermaid-container" style="width: 80%; height: 400px;">

```mermaid
flowchart TD
  %% 定义所有节点
  A[2024.10-2025.3<br>前期准备与仿真复现]
  B["2025.4<br>撰写并递交专利申请"]
  C["2025.4-6<br>完善理论分析<br>撰写论文理论与方法部分"]
  D["2025.7<br>进入实验室进行实验验证"]
  E["2025.8-9<br>撰写、修改并投递论文"]
  
  %% 使用子图分组相关活动
  subgraph 准备阶段
    A
    B
  end
  
  subgraph 研究阶段
    C
    D
  end
  
  subgraph 发表阶段
    E
  end
  
  %% 定义主要流程连线
  A --> |"前期成果积累"|B
  B --> |"学术写作训练"|C
  C -->|"理论基础支撑"| D
  D --> |"实验数据支撑"|E
  
  %% 添加A到C的额外连线
  A -.-> |"基础准备"| E
  C -.-> |"理论支持"| E

  
  %% 使用更适合学术风格的简洁样式
  style A fill:#f5f5f5,stroke:#333,stroke-width:1px
  style B fill:#f5f5f5,stroke:#333,stroke-width:1px
  style C fill:#f5f5f5,stroke:#333,stroke-width:1px
  style D fill:#f5f5f5,stroke:#333,stroke-width:1px
  style E fill:#f5f5f5,stroke:#333,stroke-width:1px
  
  %% 子图样式
  style 准备阶段 fill:#f9f9f9,stroke:#ddd,stroke-width:1px,stroke-dasharray: 5 5
  style 研究阶段 fill:#f9f9f9,stroke:#ddd,stroke-width:1px,stroke-dasharray: 5 5
  style 发表阶段 fill:#f9f9f9,stroke:#ddd,stroke-width:1px,stroke-dasharray: 5 5

```

</div>

</template>

<template v-slot:right>

# 未来工作规划

### 专利申请 (2025.4)
- 撰写专利说明书和权利要求
- 提交专利申请文件

### 理论完善与论文初稿 (2025.4-6)
- 完善理论模型和分析框架
- 进行数值仿真和初步验证
- 撰写论文的理论部分和方法部分

### 实验验证 (2025.7)
- 搭建实验平台和测试环境
- 收集实验数据并进行分析


### 论文撰写与投递 (2025.8-9)
- 整合理论和实验结果
- 完成论文撰写和修改
- 选择合适期刊并投递

</template>



---

# 目录

<div class="custom-toc">
  <div class="toc-item dimmed"><span class="toc-number">1.</span> 研究初衷与研究现状 <span style="color: #666; font-size: 0.85em;">Research Motivation & Current Status</span></div>
  <div class="toc-item dimmed"><span class="toc-number">2.</span> 前期工作与前期成果 <span style="color: #666; font-size: 0.85em;">Preliminary Work & Achievements</span></div>
  <div class="toc-item dimmed"><span class="toc-number">3.</span> 关键问题与未来工作 <span style="color: #666; font-size: 0.85em;">Key Issues & Future Work</span></div>
  <div class="toc-item highlighted"><span class="toc-number">4.</span> 申请人简历 <span style="color: #666; font-size: 0.85em;">Applicant's Resume</span></div>
</div>

---
layout: two-cols-header
---



# 申请人简历
浙江大学电气工程学院-"爱迪生"班

::left::
## 学业成绩
- 主修绩点： 4.72/5.0
- 综合绩点： 4.72/5.0
- 学业排名： <span class="blue-bold">4/152</span>

## 荣誉与奖励
- 2023-2024 学年<span class="blue-bold">国家奖学金</span>
- 2023-2024浙江大学一等奖学金
- 2023-2024 学年求是学院"新东方"奖学金
- 2023-2024 学年蓝田学园"<span class="blue-bold">十佳大学生</span>"
- 2023-2024 学年优秀学生、创新创业标兵等


::right::
## 竞赛奖项
- 2024 浙江省大学生高等数学竞赛（工科类）一等奖
- 2024 浙江省大学生物理创新竞赛二等奖
- 2024 全国大学生英语竞赛国家级三等奖

## 研究经历
- 2024-2025：校级SRTP 逆变器功率器件开路故障诊断  
            &emsp; &emsp; &emsp;&emsp;&emsp;资助金额：1200元
- 2024年10月-今：

&emsp;&emsp;在电气工程学院百人计划研究员王涛老师和国家杰青吴立建教授的指导下，<span class="blue-bold">自2024年10月</span>起从事DFIG风电系统无位置传感器控制、故障穿越相关研究

<style>
h1 {
  margin-bottom: 0.5rem !important;
}
.slidev-layout.two-cols-header {
  grid-template-rows: auto 1fr !important;
}

</style>

---
layout: end
class: thank-you-slide
---
# 诚 挚 致 谢
请各位专家批评指正！

 <style>
/* 为最后一页（致谢页）隐藏右上角的图标 */
.thank-you-slide::before {
  display: none !important;
}
</style>
