# 3D-Research

> 3D AIGC 研究进展追踪与论文深度解读 —— 覆盖 3D 生成（Generation）、3D 编辑（Editing）、3D 理解（Understanding）、部件生成（Part Generation）与统一多模态 3D 大模型等方向。

[![GitHub Pages](https://img.shields.io/badge/GitHub%20Pages-online-brightgreen?logo=github)](https://ccyyatnet.github.io/3D-research/)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)

**在线阅读：https://ccyyatnet.github.io/3D-research/**

---

## 📌 仓库简介

本仓库用于持续分享 3D 领域（3D AIGC / 3D 多模态大模型）的研究进展，每篇解读以可视化网页形式呈现，内容通常包括：

- 🧭 **相关工作图谱**：按技术路线梳理代表工作（简称 / 发表时间 / 核心贡献 / 论文与代码链接）
- 🗂️ **数据细节**：训练语料构成、数据构建流水线、涉及数据集与工具的开源情况
- 📊 **实验结果**：各任务对比指标图表化呈现 + 论文原表完整数值
- 💡 **个人评注**：核心发现、局限性与对后续工作的启发

## 📚 论文解读列表

| # | 论文 | 方向 | 发表 | 解读页面 | 备注 |
|---|------|------|------|----------|------|
| 1 | [Hunyuan3D-Buffalo 1.0: A Unified Multimodal Model for Scalable 3D Generation, Understanding, and Editing](https://arxiv.org/abs/2608.02711) | 统一 3D 多模态（理解/生成/编辑/部件） | 2026.08 | [在线解读](https://ccyyatnet.github.io/3D-research/) | 87M 语料；Nano3D-v2 数据引擎；编辑 CD ↓86.7% |

> 持续更新中，欢迎 Star / Watch 跟踪最新进展。

## 🧭 关注方向

- **3D 生成**：3D 原生潜空间生成（TRELLIS / CLAY / Hunyuan3D 系列）、自回归网格生成、Rectified Flow / Flow Matching
- **3D 编辑**：Training-free 编辑（Nano3D / VoxHammer）、训练式前馈编辑、几何一致的编辑数据构建
- **3D 理解**：3D VLM / MLLM、3D Grounding、部件级推理
- **部件生成**：开放词汇部件生成、语义部件分割与组合式生成
- **统一多模态**：AR + Diffusion 混合架构、跨任务能力迁移

## 🛠️ 如何添加一篇新解读

本站基于 GitHub Pages（`main` 分支 `/docs` 目录）部署：

```bash
# 1. 将新的解读网页放入 docs/（首页固定为 docs/index.html，子页面可放 docs/<name>/index.html）
cp new_report.html docs/<paper-name>/index.html

# 2. 提交并推送，约 1 分钟后线上自动更新
git add docs/
git commit -m "Add <paper-name> reading notes"
git push origin main
```

推送后访问 `https://ccyyatnet.github.io/3D-research/<paper-name>/`。

## 📄 License

本项目基于 [MIT License](LICENSE) 开源。网页中论文内容版权归原作者所有，本仓库仅作学习与研究分享之用。
