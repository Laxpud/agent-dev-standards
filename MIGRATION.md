# Agent Dev Standards 迁移后待办

- 已整体移入独立目录并保留隐藏文件，初始化本地 Git，默认分支为 `main`；两技能及元数据已合并，暂定版本 `1.2.0` 待发布前确认，Python 技能改用 `agent-dev-standards:pyproject-standard`。
- 已创建公开 GitHub 仓库 `Laxpud/agent-dev-standards`，核对元数据中的仓库地址，并设置仓库描述、Topics 和功能选项。
- 保留十份注释原始案例及其来源，作为维护资料，不作为技能运行依赖。
- [ ] 处理 `pyproject-standard` 无条件重复询问元数据的问题；沿用已有可靠信息，只集中询问会实质影响结果的缺失信息，保留用户要求的编辑前确认和既有配置契约。原记录见 [A4 审查](docs/reviews/2026-09-24-python-project.md)，本次清理不改技能行为。
- Vibekits 两端市场已引用本独立仓库；正式发布版本、两端客户端安装与实际执行仍需核对，旧插件安装由用户在各客户端移除。
- [x] 从 Vibekits 迁入注释与 Python 技能历史审查，入口见 [docs/index.md](docs/index.md)；A1–A3 已在此前技能改造中处理，A4 保持未完成。
