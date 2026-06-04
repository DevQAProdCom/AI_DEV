# Copilot instructions for this repository

Purpose: Provide repository-specific hints for future Copilot sessions (build/test/lint, architecture, conventions, AI integrations).

---

## 1) Build, test, and lint commands

- No project/manifest files (package.json, .csproj, pyproject.toml, etc.) were detected in this repository snapshot, and the Azure pipeline (azure-ai-pipelines.yml) is a placeholder that only echoes messages. If/when language-specific files are added, update this section.

- Common commands to add when relevant (copy into this file with concrete examples for your stack):
  - .NET (when present):
    - Full build: `dotnet build`
    - Run all tests: `dotnet test`
    - Single test: `dotnet test --filter FullyQualifiedName~Namespace.ClassName.MethodName` or use `--filter Name=TestName`
  - Node / Jest (when present):
    - Full test: `npm test` or `npx jest`
    - Single test: `npx jest path/to/file.test.js -t "name of test"`
  - Python / pytest (when present):
    - Full test: `pytest`
    - Single test: `pytest path/to/test_file.py::test_name`

- Linting: no linters configured were found. Add typical commands when enabling a linter (e.g., `dotnet format`, `npm run lint`, `flake8`, `pylint`).

---

## 2) High-level architecture (current snapshot)

- This repository currently contains only CI/agent configuration and a Visual Studio-focused .gitignore. No application source files or tests were present in the scanned tree.
- Files present that matter for Copilot sessions:
  - `azure-ai-pipelines.yml` — minimal Azure Pipelines starter YAML (triggers `main`, runs simple script steps). Treat it as a placeholder until real build/test/deploy steps are added.
  - `.mcp.json` — Model Context Protocol (MCP) server configuration (see Key Conventions below).
  - `.gitignore` — Visual Studio / .NET-oriented template: suggests the project is expected to follow Visual Studio/.NET conventions when code is added.

When source code is added, update this section with: service layout, important binaries, where tests live (e.g., `/tests`, `*/Tests/*.csproj`), key runtime components, and entry points.

---

## 3) Key conventions and repository-specific patterns

- .gitignore uses a Visual Studio/.NET template. Expect typical directories to be ignored: `bin/`, `obj/`, `.vs/`, `node_modules/`, `packages/`.
- MCP server: `.mcp.json` includes an MCP server entry named `github` that runs via `npx -y @modelcontextprotocol/server-github`. It expects a `GITHUB_PERSONAL_ACCESS_TOKEN` environment variable. Copilot sessions that use MCP features should honor that config and the required env var.

- CI: `azure-ai-pipelines.yml` currently triggers on `main` and uses `ubuntu-latest`. When adding CI steps, follow existing structure (separate build/test/deploy steps) and keep them idempotent.

- If adding multiple language projects, prefer per-language top-level folders (e.g., `src/`, `tests/`, `services/<service>/`) and add explicit docs here so Copilot can pick up tooling per subproject.

---

## 4) AI / assistant integrations found

- `.mcp.json` present: configures an MCP server that runs `npx -y @modelcontextprotocol/server-github` and requires `GITHUB_PERSONAL_ACCESS_TOKEN` in env. Leave this in place if using MCP-backed tools; update args/command if using a different MCP server.

- No other assistant-specific files (CLAUDE.md, AGENTS.md, .cursorrules, .windsurfrules, CONVENTIONS.md, etc.) were found in this snapshot. Add them here if the team adopts additional assistant tooling.

---

## 5) How to keep this file useful

- When adding language/tooling, update the Build/Test/Lint section with exact commands and examples of running a single test.
- Add brief architecture notes when services, libraries, or test frameworks are added so Copilot can give more targeted suggestions.

---

If anything in the repo changes (new language, CI, MCP servers), update this file so future Copilot sessions have accurate, actionable guidance.
