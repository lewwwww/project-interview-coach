# Project Interview Coach（项目面试教练）

一个跨平台的通用软件项目学习 Skill（Codex / Claude Code / Doubao 等均可用）：把任意代码仓库学懂、讲清，并一路带到面试现场。

**定位：通用软件项目学习。**

- 有简历 → 辅助简历（对齐目标岗位，梳理可验证的项目亮点）
- 无简历 → 参考简历模板，从项目已验证内容生成一份可用的简历
- 完整链路：**项目学习 → 八股 → 模拟面试**

## 它能做什么

对任意本地代码仓库（自己写的、课程作业、远程拉下来的开源项目都行）：

| 环节 | 能力 |
|---|---|
| 项目学习 | 通俗讲解业务与技术、验证运行方式、核心请求流转、分层架构、关键模块入口、选型与设计取舍 |
| 简历 | 有简历：把简历条目映射到代码证据，标出支持/部分支持/未验证，诚实收窄；无简历：参考模板从项目证据生成简历 |
| 八股 | 对照目标岗位 JD 或目标方向做技能差距分析，生成 gap heatmap + 学习计划（资源、顺序、时间） |
| 模拟面试 | 一问一答的递进式模拟面试，9 级提问阶梯，答后给简短评估 + 参考回答 + 下一步 |
| 沉淀 | 12 节项目学习笔记 + 三档（30 秒 / 1 分钟 STAR / 深挖）面试作战卡 |

## 核心设计原则

- **证据优先**：一切结论从仓库代码、配置、测试、运行结果而来，四级证据分级（Verified / Code-supported / Inferred / Unverified）。
- **不编造**：不虚构个人职责、生产事故、性能数字、设计意图。简历里只放有证据支撑的内容。
- **一问一答**：模拟面试一次只问一题，答后评估，不让候选人先看到完整答案。
- **反 AI 味**：讲解和面试话术追求自然、具体、可被打断，不堆砌机械口癖和空洞套话。

## 安装

这个仓库本身就是完整的 Skill 目录，按你所用 agent 的约定把它放到对应 skills 根目录下即可。三平台均可：

### Codex

Windows（PowerShell）：

```powershell
git clone https://github.com/lewwwww/project-interview-coach.git "$env:USERPROFILE\.codex\skills\project-interview-coach"
```

macOS / Linux：

```bash
git clone https://github.com/lewwwww/project-interview-coach.git ~/.codex/skills/project-interview-coach
```

装好后**新开一个 Codex 任务**才会生效。

### Claude Code

```bash
git clone https://github.com/lewwwww/project-interview-coach.git ~/.claude/skills/project-interview-coach
```

Claude Code 通过 `SKILL.md` 的 `name` / `description` / `allowed-tools` 字段自动识别本 Skill。安装后新开会话即可被上下文感知触发。

### Doubao（豆包）

Windows（PowerShell）：

```powershell
git clone https://github.com/lewwwww/project-interview-coach.git "$env:LOCALAPPDATA\Doubao\User Data\Profile 1\.doubao\agent_mode\workspace\.skills\project-interview-coach"
```

macOS / Linux：

```bash
git clone https://github.com/lewwwww/project-interview-coach.git ~/Library/Application\ Support/Doubao/.../.doubao/agent_mode/workspace/.skills/project-interview-coach
```

> Doubao 的 skills 根目录以你当前 Profile 的实际路径为准，把仓库克隆到该目录下即可；装好后新开会话生效。

### 其他遵循 SKILL.md 标准的 agent

Cline、Gemini CLI、Roo Code 等同样读取 `SKILL.md` 的 frontmatter（`name` + `description`），把本仓库放到各自的 skills 目录即可，无需改文件。

## 用法

各平台触发方式：

- **Codex：** 用 `$project-interview-coach` 前缀显式调用，或直接说下面这些自然语言指令（`agents/openai.yaml` 已开自动触发）。
- **Claude Code：** 直接说自然语言指令，Skill 按描述上下文感知自动激活；也可在提示中显式点名 `project-interview-coach`。
- **Doubao：** 直接说自然语言指令，按 Skill 描述自动匹配激活。

通用自然语言示例：

```
使用 project-interview-coach 详细、通俗地分析当前项目，验证运行方式，并结合我的简历进行面试准备。
```

或者更简单的一句：

```
帮我学习这个项目并进行模拟面试。
```

常用指令示例：

- `帮我学这个项目，输出一份项目学习笔记` —— 沉淀 12 节项目学习笔记
- `我没有简历，帮我按这个项目生成一份简历` —— 走简历生成流程（参考模板）
- `这是我的简历和一份 Java 后端 JD，帮我对齐评估` —— 走 fit 先行 + 简历优化流程
- `针对这个岗位做技能差距分析，给我一份学习计划` —— 走八股 / upskill 流程
- `开始模拟面试，从项目背景问起` —— 一问一答模拟面试

## 目录结构

```
project-interview-coach/
├── SKILL.md                          # Skill 主定义：模式选择、证据分级、分析方法（跨平台核心）
├── agents/
│   └── openai.yaml                   # Codex 专属 Agent 配置（显示名、自动触发）；其他平台自动忽略
├── references/
│   ├── project-output.md             # 12 节项目学习笔记结构 + 面试作战卡
│   ├── interview-method.md           # 简历证据映射 + 9 级提问阶梯 + 一问一答协议
│   ├── resume-workflow.md            # 简历生成 / 简历辅助工作流 + 验证清单
│   ├── upskill.md                    # 技能差距分析 + 学习计划（八股）
│   └── interview-tips.md             # STAR 素材、常见难题、反问、roleplay
├── README.md
├── CHANGELOG.md
└── LICENSE
```

## 借鉴与致谢

本 Skill 在自研方法论基础上，吸收了一批优秀开源项目的成熟设计，特此致谢：

- [MadsLorentzen/ai-job-search](https://github.com/MadsLorentzen/ai-job-search)（MIT）——候选人档案、fit 先行评估、简历验证清单、STAR / roleplay 面试准备、upskill 技能差距→学习计划
- [Egonex-AI/Understand-Anything](https://github.com/Egonex-AI/Understand-Anything)（MIT）——入口点识别、分层架构分析、引导式学习（按依赖顺序 tour）
- [0x68616F4C/real-interview](https://github.com/0x68616F4C/real-interview)（MIT）——评分复盘与反 AI 味硬规则
- [f12336414-ship-it/project-interview-extractor](https://github.com/f12336414-ship-it/project-interview-extractor)（Apache-2.0）——项目专属题库银行思路

## 注意事项

- Skill 不会自动修改项目 README，除非你明确指定。
- 简历与面试细节默认保存在外部作战卡目录，不会写入项目仓库。
- 对于无法从代码证实的说法，会明确标注为待确认（`Unverified`），不会替你编造。
- 修改本 Skill 后需**新开会话/任务**才会生效（各平台都在启动时读取 Skill 目录）。

## License

[MIT](LICENSE)
