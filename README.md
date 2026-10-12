# Agent Dev Standards

[简体中文](docs/README.cn.md)

Development standards and practices for AI coding agents, tailored to personal preferences.

This repository maintains the standalone plugin named `agent-dev-standards`, with manifests for Codex and Claude Code. The default branch is `main`; client installation and execution remain unverified. See [remaining migration work](MIGRATION.md).

## Skills

- [code-comment-standard](skills/code-comment-standard/SKILL.md)
- [pyproject-standard](skills/pyproject-standard/SKILL.md)

The current skills cover comment review and pyproject configuration. The Python skill is addressed as agent-dev-standards:pyproject-standard; its existing workflow is preserved. Original comment examples remain [maintenance material](sources/code-comment-examples/README.md).

## Installation

The source repository is `Laxpud/agent-dev-standards`. Client installation and execution using the commands below still require verification. If the repository address changes, update publisher.homepage and publisher.repository in plugin-catalog.json and both README files, then regenerate metadata with --write.

Codex, in a terminal:

~~~bash
codex plugin marketplace add Laxpud/agent-dev-standards
~~~

Then open the plugin picker and install `agent-dev-standards`:

~~~text
/plugins
~~~

Claude Code, in the client input area:

~~~text
/plugin marketplace add Laxpud/agent-dev-standards
/plugin install agent-dev-standards@laxpud-agent-dev-standards
~~~

Start a new task or session after installation. Example prompt:

~~~text
Use $agent-dev-standards:code-comment-standard to review comments in the requested files. Explain specific reading gaps and show focused rewrites without editing files.
~~~

## Maintenance

plugin-catalog.json is the metadata source. Generated manifests and local authoring marketplaces point to this repository root. Run these commands from this directory; the link checker requires an initialized Git repository:

~~~bash
python3 scripts/sync_plugin_metadata.py --write
python3 scripts/sync_plugin_metadata.py
python3 scripts/check_codex_install.py --all
python3 scripts/check_markdown_links.py
~~~

These checks verify local metadata and files; they do not prove installation or execution in either client. To check the remote files, run `python3 scripts/check_codex_install.py --all --remote --ref main`. Client installation, execution and release remain pending in MIGRATION.md. Direct npx skills distribution is not verified.

## License

[MIT](LICENSE)
