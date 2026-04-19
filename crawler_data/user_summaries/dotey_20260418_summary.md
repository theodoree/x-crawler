**新工具/技术**
- Dreamina Seedance 2.0：现在支持 1080p 下载，分阶段向付费用户推送，主要覆盖非洲、南美、中东和东南亚地区，提高视频素材质量与可用性。
- Claude Design（Anthropic）：面向设计流程的 Claude 变体，能从代码库/设计稿抽出 UI Kit 并自动套用风格，适合生成一致性高的界面稿。
- Kimi Linear / Prefill-as-a-Service：一种 hybrid attention 技术，显著压缩 KV cache，支持 Prefill/Decode 跨机房和异构硬件分离部署，降低每 token 成本。
- Hermes Agent 与 Skills 集成：Nous Research 将热门技能（如信息图）移植到 Hermes，直接在 agent 中调用提高产出效率。
- Codex Desktop APP 原生 SSH 支持：客户端可直接连接远程开发环境，方便依赖不在本机的开发场景。

**核心观点/方法论**
- 先搭设计系统再做产出：投入 1 小时构建可复用的 UI Kit 可实现风格复利，规模化推行可延长为一到两周的沉淀期，长期节省重复工作。
- 设计与工程实时协作：替代“交接式”流程，开会双方一起在画布上边聊边定稿能大幅提升落地效率。
- 区分结构级与细节级交互：结构性改动用聊天界面（多方向探索），细节用元素评论（精准快速），提高沟通效率。
- 反馈要具体量化：给模型的指令要具象（比如“表单字段间距改成 8px”），避免模糊审美类反馈以减少二次返工。
- 把上下文喂给模型：接上 Connector 把会议纪要/需求喂入 Claude，可自动产出完整解决方案，释放人力做更高阶工作。
- 关键品牌决策仍需人工把关：图标、核心插画、品牌命名这种需要审美判断的工作建议手工慢做，模型辅助而非完全替代。
- 挂代码要有选择性：不要上传整个 monorepo，挂目标组件/包并排除 .git、node_modules，避免浏览器卡顿和上下文污染。

**实践经验/案例**
- Kimi Linear 的实测数据：在 20× 放大模型上验证，带来约 1.54× 吞吐和 64% 的 P90 TTFT 降幅，证明跨机房 Prefill 可行并能降本。
- 中文搜索实务：SQLite FTS5 对中文按字分词导致跨 session 搜索失败，实用解法是用 jieba 做分词或在 FTS5 无结果时降级到 LIKE 子串匹配。
- Hermes 实战：将 Jim Liu 的 Infographic Skill 移植到 Hermes，更新后直接在会话里调用 `/baoyu-infographic <topic>` 即可生成信息图，提升产出速度。
- 远程开发优化：Codex Desktop 的 SSH 原生支持适合依赖远端环境的开发者，减少在本地复现复杂环境的成本与麻烦。