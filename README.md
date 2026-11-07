<div align="center">

<h1>Fan · AHFans</h1>

<p><strong>Power &amp; Analog IC Design × AI-assisted EDA</strong><br>
<strong>电源与模拟集成电路设计 × AI 辅助设计流程</strong></p>

<p>
<img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&amp;logo=python&amp;logoColor=white" alt="Python" height="22">
<img src="https://img.shields.io/badge/ngspice-2C3E50?style=flat-square" alt="ngspice" height="22">
<img src="https://img.shields.io/badge/Verilog--A-6f42c1?style=flat-square" alt="Verilog-A" height="22">
<img src="https://img.shields.io/badge/WSL2-0078D4?style=flat-square" alt="WSL2" height="22">
<img src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&amp;logo=docker&amp;logoColor=white" alt="Docker" height="22">
</p>

<p><strong>北京大学 硕士（2025 届） · 中国农业大学 本科</strong><br>
<strong>DRAM 电源电路设计工程师</strong></p>

<p><em>Simulation credibility · Verification automation · Reproducible measurement</em></p>

</div>

---

## What I Do · 我在做什么

在存储器产品里做**片上电源与模拟模块**的设计与验证：LDO、charge pump、bandgap、温度传感器，以及 IDD / 功耗分析。这类工作的价值不太体现在「画了多复杂的拓扑」，而体现在能不能回答下面三个问题：

- **模型能不能信** — 版图依赖效应（WPE / LDE）引起的 Vth 偏移、模型版本切换后 Monte Carlo 裕量如何变化、PVT corner 的覆盖率该怎么定。
- **验证能不能自动化** — 把重复的跨模型、跨 corner 检查变成脚本化的扫参、指标提取与报告，让人的时间花在判断上，而不是花在点鼠标上。
- **仿真能不能对得上硅** — VDDQ 纹波、PDN 阻抗、电源引起的抖动（PSIJ）与眼图指标之间，偏差究竟落在哪一层。

一句话概括方向：**用 AI 与自动化把「发现问题 → 验证 → 沉淀成规范」这条链做实，而不只是把某一个电路调得更好看。**

> 关于公开边界：本页只写通用方法与开源工程，不涉及雇主的项目细节、电路图、工艺参数、产品数据或内部仿真结果。

---

## Tech Stack · 工具与技能

| Direction | What I use |
|---|---|
| 电路与模块 | LDO / charge pump / bandgap / 温度传感器 / 片上电源网络 / IDD 与功耗分析 |
| 建模与仿真 | Verilog-A、ngspice、SPICE corner 与 Monte Carlo、行为级 ↔ 电路级对拍、OSDI 编译加载 |
| 电源完整性与 SI | VDDQ ripple、PDN 阻抗、PSIJ、eye height / eye width / DJ<sub>pp</sub> 的指标定义与提取 |
| 自动化与 AI | Python 扫参框架、自动验证脚本、指标提取与可视化、LLM 辅助设计与验证流程 |
| 工程环境 | WSL2 + Docker（IIC-OSIC-TOOLS）、开源 PDK（SKY130 / IHP）、Git |

一个自己的判断：**仿真结果的说服力来自指标定义，而不是曲线好不好看。** 所以下面这个工程里，每个指标都写了可解释的公式，分析脚本还带自检。

---

## Featured Work · 开源作品

### io-power-si-lab — 接口电源噪声 → PSIJ → 眼图，一套可复现的实验台

从零搭起来的开源等价实验：先用 level-1 MOS + Verilog-A 行为级模型把**可信的测量手段**建起来，再谈优化眼图。

- 一条命令跑完 12 组条件（4 个噪声幅度 × 3 个频率），产出波形、`metrics.csv` 与图；
- 指标全部给出明确定义，例如 `eye_height = (μ1 − 3σ1) − (μ0 + 3σ0)`，并可用 `--selftest` 校验分析链本身；
- 刻意写清了模型的适用边界：level-1 MOS 只能看趋势、驱动器只建到一阶、单周期 PRBS 不含长码 ISI、OSDI 语法随 ngspice 版本有差异。

技术栈：ngspice · Verilog-A / OSDI · Python（NumPy / Matplotlib）· WSL2 + Docker

<!-- TODO: 仓库公开前删掉下面这行；公开后确认链接有效 -->
**Repo:** [AHFans/io-power-si-lab](https://github.com/AHFans/io-power-si-lab)

### In Progress · 正在做

- **AI × 验证流程** — 把跨模型、跨 corner 的裕量检查做成可量化的表，让「这个方案要不要改」由数据说话。
- **仿真代理模型** — 用小样本仿真训练 surrogate，加速大范围扫参与眼图指标预测。
- **Auto-SPICE Agent** — LLM + ngspice 闭环，探索「定义问题 → 自动跑验证 → 判断结果」的可行性。

---

## Activity · 活跃度

<!-- 可选：第三方统计服务，加载不出或不需要时整节删除即可 -->

<p align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=AHFans&amp;show_icons=true&amp;hide_border=true" alt="GitHub stats" height="160">
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=AHFans&amp;layout=compact&amp;hide_border=true" alt="Top languages" height="160">
</p>

---

## Beyond the Bench · 工作之外

吉他指弹与弹唱。在一件完全不被 KPI 打分的事情上保持手感，是很好的校准。

---

## Contact · 联系

- 用 Issues 或 Discussions 找我最快。
<!-- TODO: 愿意公开的话，在这里补邮箱 / 城市 / 其他链接 -->

---

<sub>本页仅展示通用方法与开源工程，不含任何雇主内部信息。</sub>
