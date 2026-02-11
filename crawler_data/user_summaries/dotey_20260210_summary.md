**新工具/技术**
- OpenClaw / ClawdBot：支持一键安装 Agent Skills，能把技能包识别并安装到本地 agent，上手门槛低，便于能力扩展。  
- Vercel skills toolkit（npx skills add）：提供 skills 管理与分发的工具链，简化 skills 的安装与共享流程。  
- Seedance 2.0：近期火爆的视频生成模型，分镜与运镜能力显著提升，但存在利用公开视频训练导致的拟声/拟像问题。  
- Obsidian CLI：Obsidian 发布命令行接口，目标不是给人直接用，而是供 AI agent 调用来操作笔记库。  
- draw.io 官方 MCP server：为 agent 生态提供官方的 MCP 连接方案，方便可视化工具被 agent 控制。  
- Anthropic Claude Cowork（Windows）：Claude Cowork 推出 Windows 版，与 macOS 功能并行，增强跨平台可用性。

**核心观点/方法论**
- 工程思维优先：有工程思维的人能把散乱信息结构化、构建稳定系统，决定了使用 AI 的上限，而非仅靠最强模型。  
- AI 不会简单“替代”人：更可能是“会用 AI 的人替代不会用的人”，职业结构发生置换而非单纯裁员。  
- 隐私与数据合规要平衡：公开数据训练带来模仿/隐私风险，技术创新需与合规限制并行推进，寻找折衷方案。  
- 为 agent 开放接口是趋势：传统应用需提供可被 agent 调用的接口（CLI/MCP 等），这是可组合生态的基础。  
- 学习仍有价值：即便有实时翻译工具，掌握英语与基础能力能做校验、获取高密度信息并保持判断力。

**实践经验/案例**
- Skill->OpenClaw 实践：有人用 Vercel 的 skills 工具把 dotey 的封面图生成技能安装到 OpenClaw，端到端效果良好，验证了工具链可用性。  
- Seedance 案例教训：Tim 的测试显示，上传参考照片能生成近似其声音，说明大规模公开视频被用作训练，提醒隐私风险。  
- Obsidian CLI 的实务价值：相比 MCP 方案，CLI 更轻量且天然可被 Claude Code 等 agent 在终端执行，建议应用开发者尽早为 agent 准备接口。