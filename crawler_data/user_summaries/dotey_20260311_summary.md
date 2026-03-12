**新工具/技术**（如有）
- Claude Code — 不只是“写代码”的 coding agent，而是一个带工具链、多子 agent/skill 管理与交互模式的通用 agent 平台，支持像 /btw 这样的侧链交互。
- /btw — Claude Code 的 side‑chain 问答机制，作为无工具的降维调用并行执行，不写入主对话以避免上下文污染。
- openclaw / clawhub — 用于管理 Claude Code skill 的生态（类似 npm），但存在同名 skill 冲突与版本管理风险。
- 多个第三方 CLI（如 xiaohongshu-cli、twitter-cli 等）— 趋势是统一结构化输出（--yaml/--json）、提供 SKILL.md 以便被 AI agent 调用，并加入反风控特性（TLS 指纹、jitter、Cookie 管理）。

**核心观点/方法论**（如有）
- Claude Code 的价值不在单一能力（生成代码），而在于“工具+上下文+agent 架构”的组合能力；把它当作纯 coding agent 会严重低估其潜力。
- 设计 agent 时要兼顾并发侧路交互的可用性与主对话的缓存/一致性（/btw 用独立 API 调用+overlay 展示，实现零污染和低成本缓存命中）。
- Agent 生态需要严肃的版本和来源管理；自动化安装/升级若无确认机制，会带来严重的可解释性和安全问题（技能同名/不同内容的混乱）。

**实践经验/案例**（如有）
- /btw 的实现启示：通过 API 层禁用工具并用 system‑reminder 强化约束，既保证了功能隔离，也保持了主对话的 prompt cache 零损耗（实践上代价仅为少量 tokens）。
- Skill 管理实操风险（farmostwood 案例）：agent 自动安装/升级同名 skill 导致行为完全不一致，提示需要在 agent 中加入来源确认与安装前审查流程。
- 构建对外服务的 CLI 工具时，把输出结构化（YAML/JSON）并提供 SKILL.md，可以让上层 AI agent 更容易、安全地调用，且便于非交互场景自动化。
- 产品与工程的分工变化（转译观点）：当构建门槛下降后，产出差异更多由判断力决定——把 agent/工具能力纳入产品判断，将成为关键竞争力。