**新工具/技术**（如有）
- Claude Code 的 Hook + Skill（Stop Hook + /commit Skill）：用 Claude Code 的生命周期钩子和技能模块把“提交”变成可被代理自动完成的任务。  
- .claude/settings.local.json：用来注册 Stop Hook，触发本地脚本。  
- auto-commit.sh（Stop Hook 脚本）：用 git diff/git ls-files 检测未提交变更，返回 JSON 阻止任务结束以触发提交流程。  
- .claude/skills/commit/SKILL.md：定义 /commit 技能，自动分析变更、按主题分组并生成规范的中文 commit message。  

**核心观点/方法论**（如有）
- 用 AI 代理承担重复性 VCS 操作，降低人为忘记提交的成本，同时把提交变更变成有语义的历史记录，提升可审计性和协作效率。  
- 设计上分工明确：Hook 做守门员（检测并拦截），Skill 做执行者（如何提交、如何命名），两者配合可保证自动化既安全又有意义。  
- 自动化不是放任不管，要通过分组提交/明确文件列表/排除临时文件等规则保持变更语义清晰，避免“misc changes”式的垃圾记录。  

**实践经验/案例**（如有）
- 防止无限循环：Stop Hook 读取输入中的 stop_hook_active 标志，提交触发再次 Stop 时直接放行。  
- 变更识别规则：按路径判断类型（文章、技能、代码、配置），优先级地分组提交（文章每篇一个 commit、技能一个 commit、代码合并提交等）。  
- 提交规范：自动生成中文 commit message（“添加/润色/更新 + 主题” 或 “优化/修复 + 功能”），并明确指定要提交的文件，避免 git add .。  
- 部署位置：脚本放在 .claude/hooks/auto-commit.sh，技能放在 .claude/skills/commit，hook 在 .claude/settings.local.json 注册。  
- 实际价值：解决“写完忘记提交”的痛点，让 git log 可读、历史有上下文；实现成本低、回报高。  
- 注意事项：仓库权限（避免公开敏感内容）、磁盘空间和凭据/权限管理需谨慎设计以防泄露或风控触发。