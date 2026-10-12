# Agent Dev Standards

[English](../README.md)

基于个人偏好的 AI 编程代理开发规范与实践。

本仓库维护独立插件 `agent-dev-standards`，提供 Codex 和 Claude Code 的 manifest，默认分支为 `main`；两端客户端安装与实际执行尚未验证。剩余迁移工作见[迁移后待办](../MIGRATION.md)。

## 技能

- [code-comment-standard](../skills/code-comment-standard/SKILL.md)
- [pyproject-standard](../skills/pyproject-standard/SKILL.md)

当前技能涵盖注释审查与 pyproject 配置，Python 技能的调用名为 agent-dev-standards:pyproject-standard，现有技能流程保持原样。[注释原始案例](../sources/code-comment-examples/README.md)只供维护时参考。

## 安装

源码仓库为 `Laxpud/agent-dev-standards`。下方命令在两端客户端中的安装与实际执行仍待验证；若地址变更，同步修改 plugin-catalog.json 的 publisher.homepage、publisher.repository 和中英文安装命令，再重新生成元数据。

在终端添加 Codex marketplace：

~~~bash
codex plugin marketplace add Laxpud/agent-dev-standards
~~~

在 Codex 输入区打开列表，安装 `agent-dev-standards`：

~~~text
/plugins
~~~

在 Claude Code 输入区依次执行：

~~~text
/plugin marketplace add Laxpud/agent-dev-standards
/plugin install agent-dev-standards@laxpud-agent-dev-standards
~~~

安装后新建任务或会话。最小提示词：

~~~text
Use $agent-dev-standards:code-comment-standard to review comments in the requested files. Explain specific reading gaps and show focused rewrites without editing files.
~~~

## 维护

plugin-catalog.json 是元数据维护入口；两端 manifest 和用于独立调试的 marketplace 均由脚本生成，指向本仓库根目录。链接检查要求目录已初始化 Git；从本目录运行检查：

~~~bash
python3 scripts/sync_plugin_metadata.py --write
python3 scripts/sync_plugin_metadata.py
python3 scripts/check_codex_install.py --all
python3 scripts/check_markdown_links.py
~~~

以上只检查本地元数据和文件，不代表两端客户端安装或实际执行已通过。检查远端文件可运行 `python3 scripts/check_codex_install.py --all --remote --ref main`。客户端安装、实际执行与正式发布保留为 MIGRATION.md 中的待办；npx skills 分发尚未验证。

## 许可证

[MIT](../LICENSE)
