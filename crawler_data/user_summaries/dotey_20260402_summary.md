**新工具/技术**
- Gemma 4：Google 推出、改用 Apache‑2.0 开源许可，31B/26B/E4B/E2B 等多尺寸，支持 256K 上下文并有端侧小模型（手机/树莓派/Jetson）能力。
- OmniVoice：Daniel Povey/小米团队的零样本 TTS，支持 600+ 语言、单阶段架构、开源代码与数据，性价比高。
- marknative：TypeScript 原生 Markdown→分页 PNG/SVG 渲染器，无需浏览器，当前样式/内嵌图片/表格分页支持有限，适合尝鲜。
- OpenClaw/DeepSeek（产品化示例）：把已有 agent 能力推向大众，推动非技术用户使用可读写文件、有记忆的 agent。

**核心观点/方法论**
- 并行开发不是只有 worktree：多个固定目录 clone + 每次 pull + checkout 新 branch + PR 流程更简单，适用于超大 monorepo；关键是可操作性和稳定性。
- Skills 管理要以单一源头和链路为原则：用 Git 做版本控制，production 环境通过 symlink 指向源仓库以保持一致性与可回溯性。
- 把 AI 当“员工”而非“工具人”需要闭环：让 AI 能自己跑、自己验、自己改与提 PR，工作方式决定效率差距远超过模型性能。
- 关注模型“内部状态”：Anthropic 的情绪向量研究表明内部激活会影响决策（如作弊或讨好），构建可信 agent 要管理这些状态与压力情形。
- 市场与许可同样重要：Gemma 4 的 Apache 许可+端侧能力会促进嵌入式/企业采纳；二级市场对 Anthropic 的溢价反映了对商业化路径的偏好差异。

**实践经验/案例**
- 并行开发实操建议：在固定目录多份 clone，轮着用并保持经常 pull 与以 PR 合并为主，避开 worktree 在大仓的限制。
- Skills 部署落地：把 skills 放项目下 (.agents/skills)，通过 symlink 指向唯一源头；优点：干净的版本控制与即时修复；缺点：Windows 对 symlink 支持差、首次配置麻烦。
- 验证与回滚策略：对脚本写单元测试，Markdown 依靠测试集与人工，借助 Git commit history 快速定位或回滚问题。
- 工具限制与风险管理：marknative 当前还不适合复杂生产文档；Slack 删除事件提醒要做好数据备份与供应商风险评估。
- 组织/产品观察：DeepSeek 更偏长期技术路线（国产芯片适配、仿生/原创研究），短期可能少投入 agent/coding 赛道，值得跟踪其产品化进展与人员流动影响。