# Agent Dev Standards 迁移后待办

- 已整体移入独立目录并保留隐藏文件，初始化本地 Git，默认分支为 `main`；两技能及元数据已合并，暂定版本 `1.2.0` 待发布前确认，Python 技能改用 `agent-dev-standards:pyproject-standard`。
- 已创建公开 GitHub 仓库 `Laxpud/agent-dev-standards`，核对元数据中的仓库地址，并设置仓库描述、Topics 和功能选项。
- 保留十份注释原始案例及其来源，作为维护资料，不作为技能运行依赖。
- 另行处理 `pyproject-standard` 无条件重复询问元数据的问题，本次迁移不顺带改行为。
- 正式发布前确定合并后的新版本，检查两端客户端安装与实际执行；验证通过后再切换日常安装的市场来源、移除旧 `python-project` 条目。
