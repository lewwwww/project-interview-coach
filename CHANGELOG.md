# Changelog

本文件记录 `project-interview-coach` 的显著变更。格式遵循 [Keep a Changelog](https://keepachangelog.com/zh-CN/1.1.0/)，版本遵循 [Semantic Versioning](https://semver.org/lang/zh-CN/)。

## [Unreleased]

### Added

- **项目拉取目录偏好**：SKILL.md 新增 Project Location Preference——学习远程项目且未指定路径时，默认克隆到 `D:\计算机项目学习\<repo-name>`（本地偏好，不可移植）。
- **跨平台兼容**：SKILL.md 增加 `allowed-tools` 字段（Claude Code 识别）；README 改为 Codex / Claude Code / Doubao 三平台安装与用法说明（`agents/openai.yaml` 标注为 Codex 专属，其他平台忽略）。
- 新增 `references/resume-workflow.md`：简历工作流（有简历→fit 先行评估+优化；无简历→参考模板从项目证据生成）+ 简历验证清单。
- 新增 `references/upskill.md`：技能差距分析（gap heatmap）→ 八股学习计划（资源 / 顺序 / 时间），衔接已有题库积累。
- 新增 `references/interview-tips.md`：STAR 素材模板、常见难题、反向提问清单、roleplay 指南、电话/视频面试技巧。
- 项目学习环节强化：引入入口点识别、分层架构分析、引导式学习（按依赖顺序），并入 `references/project-output.md`。
- 新增 `README.md`（新定位：通用软件项目学习 + 简历 + 八股 + 模拟面试）与 `LICENSE`（MIT）。
- `SKILL.md` 增加“简历生成 / 八股计划”两个可选模式，并在 Communication Style 增加反 AI 味硬规则。
- `agents/openai.yaml` 的默认提示词与新定位同步。

## [0.1.0] - 2026-09-04

### Added

- 初始版本：六模式（项目讲解 / 简历重点 / 模拟面试 / 场景题 / 代码追问 / 沉淀文档）。
- 四级证据分级：Verified / Code-supported / Inferred / Unverified。
- 9 级项目提问阶梯与一问一答模拟面试协议。
- 12 节项目学习笔记结构与三档面试作战卡（30 秒 / 1 分钟 STAR / 深挖）。
- 默认输出目录偏好：`D:\yy的成长记录\30-工作准备\项目\面试作战卡\`。
