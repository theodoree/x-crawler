**新工具/技术**
- Recordly — 开源、跨平台的 Screen Studio 替代品，免费且据测比原商用软件更轻便流畅，可直接节省上千人民币。
- baoyu-slide-deck（baoyu-skills）— 可把 PDF 或素材路径转成手绘风格的 Slides，方便快速生成有风格的演示稿。
- DESIGN.md（58 个大厂风格集合）— 把品牌风格作为项目文件丢给 AI，可以强制输出特定审美，快速提升前端/UI 一致性。
- Anthropic advisor tool（advisor_20260301）— 在同一次请求内把便宜的执行模型（Sonnet/Haiku）与昂贵顾问模型（Opus）配对，自动决策请教，节省成本且提升关键决策质量。
- OpenAI 新 Pro 档（$100/月）— 针对重度 Codex 用户的订阅层，提供更高的 Codex 用量配额。
- Claude Code 配置开关 — 提供 CLAUDE_CODE_DISABLE_1M_CONTEXT 与 CLAUDE_CODE_AUTO_COMPACT_WINDOW 等环境变量，方便控制上下文长度与自动压缩策略。

**核心观点/方法论**
- 用“便宜模型做大多数、昂贵模型把关关键点”能显著降本且保留核心智能：Anthropic 的顾问模式就是这一思路的工程化实现。
- 通过直接给 AI 一个现成风格模版（DESIGN.md）比教它“什么是好看”更高效——把审美规则作为输入，比训练或提示更可靠。
- 产品/订阅层化反映使用场景：按实际 Codex 用量选择订阅比“盲目更大配额”更经济。
- 遇到性能/行为争议时先给出可控配置让用户验证（例如禁用 1M 上下文），比基于直觉断言更科学。

**实践经验/案例**
- Anthropic 实测：Sonnet+Opus 在 SWE-bench 提分约 2.7 个百分点并降本 ~11.9%；Haiku+Opus 在 BrowseComp 从 19.7% 提到 41.2%，成本仅为 Sonnet 的 ~15%，适合大规模低成本场景。
- Recordly 实测比 Screen Studio 更顺滑，跨平台且免费，直接替代商用录屏可节省约 1500+ 人民币。
- 操作性小贴士：在 ~/.claude/settings.json 中设置 CLAUDE_CODE_DISABLE_1M_CONTEXT=1 或调整 CLAUDE_CODE_AUTO_COMPACT_WINDOW（如 200000）可以立刻控制上下文行为，便于调优体验与成本。