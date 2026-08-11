# 3D-Research

> 3D AIGC 研究进展追踪与论文深度解读 —— 覆盖 3D 生成（Generation）、3D 编辑（Editing）、3D 理解（Understanding）、部件生成（Part Generation）与统一多模态 3D 大模型等方向。

[![GitHub Pages](https://img.shields.io/badge/GitHub%20Pages-online-brightgreen?logo=github)](https://ccyyatnet.github.io/3D-research/)
[![License](https://img.shields.io/badge/license-Apache%202.0-blue.svg)](LICENSE)

**在线阅读：https://ccyyatnet.github.io/3D-research/**

---

## 📌 仓库简介

本仓库用于持续分享 3D 领域（3D AIGC / 3D 多模态大模型）的研究进展。站点采用「门户 + 子页面」结构：首页为内容导航门户，每篇内容一个独立子页面。内容形式分两类：

**📖 论文深度解读**（单篇论文精读）：
- 🧭 **相关工作图谱**：按技术路线梳理代表工作（简称 / 发表时间 / 核心贡献 / 论文与代码链接）
- 🗂️ **数据细节**：训练语料构成、数据构建流水线、涉及数据集与工具的开源情况
- 📊 **实验结果**：各任务对比指标图表化呈现 + 论文原表完整数值
- 💡 **个人评注**：核心发现、局限性与对后续工作的启发

**🛰️ 前沿追踪合集**（按方向/时段聚合）：
- 定期检索 ArXiv 最新论文，按子方向分类梳理，附发表时间、亮点与趋势观察

## 📚 内容列表

| # | 内容 | 类型 | 方向 | 日期 | 页面 | 备注 |
|---|------|------|------|------|------|------|
| 1 | [Hunyuan3D-Buffalo 1.0: A Unified Multimodal Model for Scalable 3D Generation, Understanding, and Editing](https://arxiv.org/abs/2608.02711) | 📖 深度解读 | 统一 3D 多模态（理解/生成/编辑/部件） | 2026.08 | [在线解读](https://ccyyatnet.github.io/3D-research/buffalo/) | 87M 语料；Nano3D-v2 数据引擎；编辑 CD ↓86.7% |
| 2 | 2026 年 6 月以来 3D 生成论文速览 | 🛰️ 追踪合集 | 文/图生 3D、FF-3DGS 重建、场景生成、部件纹理 | 2026.08 | [在线速览](https://ccyyatnet.github.io/3D-research/3d-generation-2026/) | 收录 25 篇；5 个方向；含趋势观察 |
| 3 | [TRELLIS 2: Native and Compact Structured Latents for 3D Generation](https://arxiv.org/abs/2512.14692) | 📖 深度解读 | 3D 表示 / 图生 3D / PBR 纹理生成 | 2025.12 | [在线解读](https://ccyyatnet.github.io/3D-research/trellis2/) | O-Voxel 任意拓扑+PBR；SC-VAE 16× 压缩；用户偏好 66.5%；全开源 |
| 4 | [EditFlow3D: Automated Local Editing of 3D Assets with Trajectory Preservation](https://arxiv.org/abs/2608.03179) | 📖 深度解读 | 3D 局部编辑（免训练） | 2026.08 | [在线解读](https://ccyyatnet.github.io/3D-research/editflow3d/) | DFG+TPG 软约束；EditFlow-Bench；PSNR 36.53 |
| 5 | 3D 透明材质表示形式全景调研 | 📋 调研报告 | 渲染 / 透明材质表示 | 2026.08 | [在线调研](https://ccyyatnet.github.io/3D-research/transparent-materials/) | A~F 六类 14 种方案；对比矩阵 + 选型建议 |

> 持续更新中，欢迎 Star / Watch 跟踪最新进展。

## 🧭 关注方向

- **3D 生成**：3D 原生潜空间生成（TRELLIS / CLAY / Hunyuan3D 系列）、自回归网格生成、Rectified Flow / Flow Matching
- **3D 编辑**：Training-free 编辑（Nano3D / VoxHammer）、训练式前馈编辑、几何一致的编辑数据构建
- **3D 理解**：3D VLM / MLLM、3D Grounding、部件级推理
- **部件生成**：开放词汇部件生成、语义部件分割与组合式生成
- **统一多模态**：AR + Diffusion 混合架构、跨任务能力迁移

## 📄 License

本项目基于 [Apache License 2.0](LICENSE) 开源。网页中论文内容版权归原作者所有，本仓库仅作学习与研究分享之用。
