# Resume Mapping And Interview Method

Read this reference when a resume is provided or the user requests resume focus, code follow-ups, scenarios, or interview practice.

## Resume Evidence Map

For each material statement, capture:

| Resume claim | Role relevance | Code/config evidence | Status | First question | Deep follow-up | Honest adjustment |
|---|---|---|---|---|---|---|
| Exact wording | High/medium/low | Paths and symbols | Supported/partial/unverified | Concrete opening | Scenario or principle | Narrowing or boundary statement |

Scrutinize strong verbs such as “designed”, “owned”, “optimized”, and “solved”, plus every metric. Code may prove implementation but usually cannot prove personal ownership or production impact.

## Project-Grounded Question Ladder

Move through the ladder based on the user's answer rather than asking everything mechanically:

1. **Overview:** What problem does the project solve, for whom, and why?
2. **Responsibility:** What did the user personally own, change, test, or coordinate?
3. **Concrete path:** Walk through the endpoint, function, table, event, configuration, and downstream calls.
4. **Decision:** Why this design, what alternatives existed, and what was traded off?
5. **Failure:** What happens with bad input, dependency failure, retry, duplicate request, partial completion, or inconsistent data?
6. **Scale:** What changes with more traffic, data, concurrency, latency, or memory pressure?
7. **Diagnosis:** Which logs, metrics, tests, traces, or tools isolate the cause?
8. **Fundamentals:** Connect behavior to transactions, concurrency, networking, memory, data structures, or framework internals.
9. **Reflection:** What should improve, under which trigger, and at what cost?

For a Redis resume claim, locate the exact cache implementation and ask about key design, lookup flow, misses, source-of-truth access, write-back, expiry, invalidation, penetration, breakdown, avalanche, and consistency. Mention these only when connected to the actual code or clearly framed as a hypothetical extension.

For system-design scenarios, clarify data size, concurrency, latency, consistency, availability, and cost before selecting a solution.

## One-Question Protocol

Each mock-interview turn contains:

1. A short assessment of the previous answer, except on the first turn.
2. One or two material omissions.
3. A concise, conversational reference answer grounded in project evidence.
4. Exactly one next question.

Do not reveal a long answer key before the user responds. If the answer is weak, give a small hint and remain at the same depth. If it is solid, deepen with a failure, tradeoff, or fundamental. Move laterally when more depth is irrelevant to the target role.

## Evaluation Dimensions

Evaluate observable content rather than personality:

- Technical foundations connected to the project.
- Understanding of business flow and system boundaries.
- Accuracy about personal responsibility.
- Problem decomposition, diagnosis, and verification.
- Design tradeoffs and engineering quality.
- Clear, structured, concise communication.

For junior candidates, prioritize foundations, learning, implementation clarity, and honest problem solving. For experienced candidates, increase emphasis on business decisions, ownership, reliability, scale, and cross-team tradeoffs.

## Role Adaptation

- **Java backend:** controllers, services, persistence, transactions, authentication, caches, queues, microservice calls, concurrency, JVM behavior, observability, and recovery when present.
- **General development:** actual stack, data flow, interfaces, testing, maintainability, and failure modes.
- **Testing:** requirements, test design, boundaries, automation, defect isolation, regression, and risk.
- **AI/CV:** data, preprocessing, model input/output, evaluation, serving, latency, reproducibility, and error analysis.

Never assume a technology because it is common for the role. Derive questions from the repository and resume first, then deepen with fundamentals.

## Honest Boundary Language

- “这部分不是我主要负责的，我能讲清楚它和我负责模块之间的调用与数据流；我实际完成的是……”
- “仓库能确认当前实现，但不能只凭代码确认当时的选型过程。我会把能看到的取舍和我的理解分开说。”
- “这个指标写在简历里，但现有材料没有测试报告支撑。面试前需要补证据，否则建议弱化成可验证的结果。”

The goal is not to cover every possible question. Make a small number of important projects defensible, concrete, and easy to explain under interruption.

