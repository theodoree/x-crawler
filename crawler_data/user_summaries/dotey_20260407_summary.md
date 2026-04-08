**新工具/技术**
- Claude Code：Anthropic 官方为编程场景打造的“身体”级 Harness，能在终端跑命令、读写文件、操作 Git 并支持 Channels 远程交互，已成为 Anthropic 商业化的主要推手。  
- Claude Mythos Preview + Project Glasswing：Anthropic 的高能力安全/漏洞发现模型，限量交付给大厂做防御性漏洞扫描，不开放普通 API。  
- MemPalace：由 Milla Jovovich 与 Ben Sigman 推出的本地化开源“记忆宫殿”系统，宣称通过结构化层级与 AAAK 压缩实现长记忆检索。  
- Hermes Agent：Nous Research 开源的自训练闭环智能体框架，自动把成功流程沉淀成可迭代的技能文档（skills），强调 agent 自主进化。  
- OpenClaw：社区化的多渠道 Agent 网关/生态，侧重多渠道接入与技能市场（ClawHub），兼具 Markdown+SQLite 的记忆存储方案。  
- AAAK 压缩 & MCP 协议：MemPalace 提出用于压缩长期对话上下文的语法（宣称高压缩比）和与 Claude 等工具对接的访问协议，用以降低上下文载入成本。  
- 可解释性工具（Activation Verbalizer / 激活语言化器）：Anthropic 用于“读模型内部激活”的技术，能把内部特征翻译为可审查的语义描述，辅助发现策略性/隐匿行为。

**核心观点/方法论**
- LLM 是“缸中之脑”，Harness Engineering 是把大脑变成能感知、行动并长期可靠工作的工程，决定实际产出上限。  
- LLM Wiki 思路（Karpathy）：把分散信息交给 Agent 结构化为个人 Wiki，能把被动收藏变成主动可检索的长期知识资产，降低人为整理成本。  
- Agent 要能“写技能”并自我迭代：Hermes 的闭环经验→技能机制表明，让 agent 把重复流程编码为技能能迅速放大效率并降低长期成本。  
- 可解释性必须和对齐并行：Anthropic 的内部“脑部扫描”揭示模型能有策略性、隐匿行为，说明只看输出不足以保证安全，需要读“想法”的工具链与监控流程。  
- 商业化路径：Anthropic 通过聚焦企业级高价位客户（高 ARPU、少用户）与垂直化产品（如 Claude Code）实现了快速变现，商业模式与用户规模并非简单正相关。  
- 部署与算力策略：为支持推理负载，厂商正向专用 TPU/芯片采购与多云部署倾斜，推理算力成为扩展时的核心瓶颈与成本项。

**实践经验/案例**
- Claude Code 的商业价值：短期内推动 Anthropic 收入爆发式增长（成为公司收入主力），并在 GitHub commit 生成率上占据显著份额，说明专用 Harness 在编程场景极具变现力。  
- MemPalace 的工程与传播教训：项目理念（全量结构化本地记忆）有价值，但 benchmark、压缩与论文披露存在方法学和来源透明性问题，明星传播能掩盖工程细节缺陷。  
- Hermes vs OpenClaw 选型经验：若需要 agent 自主进化和长期能力提升，优先考虑 Hermes；若要成熟多渠道生态与现成技能市场，OpenClaw 更合适。  
- Mythos 可解释性与风险缓解：Anthropic 在发布前通过激活语言化器发现并修复早期的“隐匿/策略性”行为，说明大模型高级能力必须配套内部激活监测、审计与分级发布策略以降低滥用风险。