**新工具/技术**（如有）
- Vercel Open Agents — 开源的编程 Agent 参考实现，三层架构（前端会话、持久化 Agent workflow、沙箱执行），Agent 不在沙箱内而是通过工具远程操作沙箱，便于独立演进模型/沙箱/Agent 生命周期。  
- Anthropic Managed Agents / Claude Code Routines — 托管型 Agent 平台，支持 Routines（定时 / GitHub 事件 / API 触发），带有 prompt caching、上下文压缩、自动恢复等 harness 优化，但锁定 Claude 模型与 Anthropic 基础设施。  
- Claude Code 桌面重构 & worktree 会话隔离 — 桌面端优化并行会话与多个并行任务，自动用 Git worktree 隔离修改，便于并行化开发。  
- khazix-skills（hv-analysis / khazix-writer）— 开源的研究与写作 Skill 套件，能做纵横向深度调研并输出高质量文章模版与自检流程，适合把研究流程工程化。

**核心观点/方法论**（如有）
- “软件工程 First”胜过盲目 AI First — AI 能大幅提升产出速度，但没有扎实的测试、CI/CD、监控、模块化与任务管理，AI 产出只会堆成烂摊子。重要因为工程基础决定能否安全、可控、可恢复地放大 AI 的效率。  
- Agent 与执行环境必须分离 — 把“脑”（模型/调度）和“手”（沙箱/容器/执行环境）拆开，容器不再是“宠物”，提升可替换性、安全性与可恢复性。  
- 人机结对、不要过早放手 — 高质量产出需要人类愿景、引导与品味，自动化应保留 human-on-the-loop 的关键判断点。  
- 投资模块化+严密验证循环（harness engineering）是核心实践原则 — 模块化降低上下文复杂度，验证循环保证每次自动化改动可被快速检测与回滚。

**实践经验/案例**（如有）
- Vercel Open Agents vs Anthropic Managed — 开源实现给出“可 fork、可自托管”的起点；托管服务换来内建优化与易用性，但牺牲模型/底层控制权与可定制性。  
- Claude Code Routines 的价值 — 把常见工程杂活（文档同步、PR 审查、报警排查）变成事件驱动的自动化 Agent，执行以用户身份操作需注意权限配置与配额。  
- haicode 的 Harness 实践（四步 PRD 流程）— 用 PRD 做中间层把上游实现与本项目差距拆成可执行 plan，再逐步细化与执行，能把“模糊需求→可交付任务”工程化。  
- khazix 的横纵分析与写作 Skill 流水线 — 把深度研究和写作分层工具化，强调反向约束（告诉模型不能做什么）和人机分工，提升产出质量与可信度。  
- 风险与适用场景 — 适合后端驱动、数据可量化、快速试错的产品；不适合 UI 密集、强交互或高安全要求的核心系统。  
- 操作建议（实用且危险低）— 先补自动化测试、打通 CI/CD、做 A/B 与监控、拆小任务并建立权限与回滚机制；否则 AI 的速度会反噬质量。