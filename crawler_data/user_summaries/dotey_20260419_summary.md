**新工具/技术**（如有）
- baoyu-infographic skill — dotey 在 ClawHub/Agent 生态里的信息图生成技能，能直接用 /baoyu-infographic + <URL> 生成高质量信息图。  
- Hermes Agent（NousResearch） — 作为运行 agent 的平台，用来调用并测试上述信息图技能。  
- Claude Agent / GitHub Copilot Agent 的“Allow Dangerously Skip Permissions”设置 — 可在本地沙箱中关闭权限确认，从而让 agent 跳过权限审批（有安全风险，仅限无网沙盒）。  
- GPT Image 2（被转发用于生成城市海报）— 用于生成复杂的海报级图像，示例显示能做双重曝光与细节合成。

**核心观点/方法论**（如有）
- 开源技能治理与所有权问题很严重 — dotey 指出有人直接 fork 并发布其开源代码，导致原作者无法在 ClawHub 使用原 slug，平台协助不力可能让作者停止发布。重要性：破坏开源生态信任和开发者积极性。  
- AI 生成中文常有“翻译腔”问题 — 原理是模型先用英文句法思考再直译成中文，解决策略是用中文思路重写而不是修补。重要性：影响可读性与专业表达。  
- 多语 LLM 的决策可能偏向接近英文的表示空间 — 有学术支持说明关键决策在接近英语的表示中发生，提示在做多语应用和 prompt 设计时需注意语言表征差异。

**实践经验/案例**（如有）
- slug 被劫持的真实案例：dotey 多次向 ClawHub 申诉（自 3 月 9 日起），但无实质进展，影响到技能发布策略与用户使用便利。  
- baoyu-infographic 的实测反馈很好：在 Hermes Agent 中用 URL 一键生成信息图，用户体验与效果优于部分传统绘图技能。  
- 权限跳过的小技巧：在 Claude Agent 设置中勾选 Allow bypass permissions 并在对话权限选 Bypass Approvals 可以避免频繁确认，但仅推荐在无外网的沙盒环境使用以防安全问题。  
- 社区传播与反响：相关推文有较多互动与引用，说明这个问题和工具在开发者/用户群中有较高关注度。