# Project Study Output

Read this reference for a full project walkthrough, interview battle card, or document update.

## Evidence-First Workflow

Build conclusions from repository instructions and maintained docs; manifests, scripts, configuration, migrations, and deployment files; traced runtime paths; tests, logs, error handling, comments, and version-control history; then resume or preparation notes.

Run only safe, relevant commands. A successful build is not proof that the application starts, and a successful start is not proof that every dependency works. Record exactly what was verified.

## Choose The Destination First

Do not assume the project README is the destination. If the user has not supplied a path, ask them to choose among:

1. **Recommended on the original machine when the directory exists:** `D:\yy的成长记录\30-工作准备\项目\面试作战卡\<项目名>-面试作战卡.md`.
2. A path specified by the user.
3. The project root `README.md`.

On a shared installation where the original-machine directory does not exist, ask the recipient for their preferred interview-notes directory and recommend `<chosen-directory>\<项目名>-面试作战卡.md`. Do not create the original user's `D:\yy...` directory on another machine.

Do not write until the destination is selected. When using the recommended directory, derive `<项目名>` from the repository root name and let the user correct it through their selection. Create the directory or file only after selection.

Preserve unrelated existing material at the selected destination. If the project README is selected, append or update a clearly delimited study section without overwriting project-owned content.

## Project Study Structure

Write this exact structure to the selected destination, omitting no heading but saying “暂未确认” when evidence is insufficient:

```markdown
# 项目学习笔记

## 1. 这个项目是干什么的
## 2. 如何在本地运行
## 3. 一次核心业务请求是怎么流转的
## 4. 整体技术架构
## 5. 关键模块与代码入口
## 6. 框架和组件分别解决了什么问题
## 7. 为什么这样选型
## 8. 关键设计与取舍
## 9. 难点、历史问题和遗留 Bug
## 10. 与我的简历经历对应的重点
## 11. 面试官可能怎么问
## 12. 结合具体代码的场景题
```

Content requirements:

- Every section is substantive. Cover what it means, project evidence, step-by-step behavior, reasons and tradeoffs, realistic scenarios or boundaries, and interview wording wherever applicable.
- Explain each technical term in plain language on first use, then identify its role in this repository. Do not replace a project explanation with a generic framework definition.
- Use enough detail that the user can reconstruct the main flow without reopening every source file. Depth comes from evidence and causal explanation, not repeated prose.
- When evidence is insufficient, state the missing fact, current inference, and a concrete verification method. Do not silently shorten or fabricate the section.

- Section 2 distinguishes verified commands from commands inferred from project files.
- Sections 3 and 5 cite paths and symbols and show the actual call or data flow.
- Sections 6 through 8 explain problems solved, alternatives, and tradeoffs, not just component definitions.
- Section 9 includes historical problems only when commits, issues, tests, logs, comments, or the user establish them. Otherwise list code risks or realistic diagnostic scenarios with explicit labels.
- Section 10 maps resume claims to code evidence without exposing unnecessary personal details.
- Sections 11 and 12 derive questions from this project. Avoid generic trivia that could apply to any repository.

## Section-Specific Depth

1. **项目是什么:** users, pain point, main capabilities, inputs, outputs, boundaries, and a plain one-sentence explanation.
2. **本地运行:** prerequisites, versions, dependencies, environment variables without secrets, exact commands, startup order, verification signal, common failure, and verified/inferred status.
3. **核心请求:** initiating action, endpoint, validation, service calls, persistence or messaging, response, errors, and a path-and-symbol call chain.
4. **整体架构:** layers or services, ownership boundaries, communication, data stores, external systems, deployment shape when evidenced, and why the structure fits the project.
5. **模块与入口:** responsibilities, important files and symbols, upstream/downstream relationships, and the recommended reading order.
6. **框架与组件:** the problem each solves, how this project configures and calls it, what breaks without it, and relevant limitations.
7. **选型原因:** evidenced intent or clearly marked inference, alternatives, advantages, costs, and the conditions under which another option would be preferable.
8. **设计与取舍:** key abstractions, consistency, performance, maintainability, security, and complexity decisions with concrete consequences.
9. **难点与问题:** symptom, impact, evidence, diagnosis, root cause, resolution, verification, and prevention for confirmed issues; separate likely risks and hypothetical scenarios.
10. **简历重点:** exact claim, code evidence, responsibility boundary, supported/partial/unverified status, natural answer, and likely follow-up.
11. **面试问题:** opening question, what it tests, answer outline, evidence anchors, common weak answer, and one deeper follow-up.
12. **代码场景题:** exact code location and current flow, changed operating condition, expected risks, analysis path, solution options, tradeoffs, and verification plan.

Keep personal resume analysis and interview scoring in the external battle-card file by default. Put them in a repository file only when the user explicitly selects that destination. Never include speculative bugs or fabricated production stories as facts.

## Interview Battle Card

Prepare spoken material at three depths:

- **30 seconds:** what the project is, defensible personal contribution, main technology, and evidenced result.
- **1 minute:** Situation, Target, Action, and Result, with the Action receiving the most detail.
- **Deep dive:** one end-to-end feature, one important choice, one evidenced challenge or labeled scenario, one engineering-quality topic, and one conditional improvement.

Use prompts rather than long scripts. Start broad, then narrow. Quantitative statements require a source or an `Unverified` label.

“Add Redis/MQ/Elasticsearch” is not a valid optimization by itself. Explain the bottleneck, expected benefit, correctness cost, operational cost, and the signal that would justify the change.

When several projects are available, prepare at most one or two deeply. Rank them by target-role relevance, personal contribution, available evidence, and user familiarity.
