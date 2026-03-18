# OpenShell Research: Official Sources

Date: 2026-03-18
Scope: NVIDIA docs, GitHub releases, and PyPI metadata

## What OpenShell Is

NVIDIA positions OpenShell as an open-source runtime for autonomous AI agents that execute inside sandboxed environments with policy-based controls. The stated security model combines filesystem restrictions, network policy, process constraints, and managed inference routing.

NVIDIA officially announced OpenShell in a technical blog post dated 2026-03-16 and presented it as part of the broader NemoClaw stack.

## Naming Collision to Ignore

Generic searches for "NVIDIA OpenShell" can also hit older NVIDIA networking and preboot-driver documentation where `OPEN_SHELL` refers to an iPXE or firmware shell behavior. That is a different product area. For this workspace, the relevant product is the agent runtime documented at `docs.nvidia.com/openshell` and the `NVIDIA/OpenShell` GitHub repository.

## Architecture Notes

- Main components: gateway, sandbox, policy engine, privacy router
- Local mode runs the gateway inside Docker on the workstation
- The runtime uses a K3s cluster inside a Docker container; no separate Kubernetes install is required for the default local path
- Network and inference policies are hot-reloadable; filesystem and process rules are locked at sandbox creation

## Platform and Runtime Notes

- Supported host platforms from the support matrix:
  - Linux Debian/Ubuntu on amd64
  - Linux Debian/Ubuntu on arm64
  - macOS on Apple Silicon via Docker Desktop
  - Windows x86_64 via WSL2 plus Docker Desktop, marked experimental
- Docker Desktop or Docker Engine 28.04+ is listed as a prerequisite
- PyPI metadata currently lists Python `>=3.12`

## Agent Notes

- Official supported-agents documentation says:
  - Claude Code: full default policy coverage
  - OpenCode: partial coverage
  - Codex: no default coverage; requires custom policy and `OPENAI_API_KEY`
  - OpenClaw and Ollama: provided through community sandboxes
- Quickstart documentation, however, presents `openshell sandbox create -- codex` as a normal first-run flow
- PyPI project text also presents Codex as a standard sandbox target

## Release and Maturity Signals

- NVIDIA technical blog launch date: 2026-03-16
- GitHub releases show `OpenShell v0.0.10` as the latest visible release on 2026-03-18
- PyPI currently shows `openshell 0.0.7` released on 2026-03-17
- PyPI classifies the project as `Development Status :: 3 - Alpha`
- The public release cadence is very fast, which is useful for momentum but increases the chance of setup churn

## Local Project Implications

- Start with a documentation-led local evaluation instead of assuming stable installation behavior
- Treat macOS support as viable but still actively changing
- Do not assume Codex is fully covered until the policy story is tested end-to-end
- Prefer a non-GPU first milestone unless GPU passthrough is a hard requirement

## Open Questions

1. Which upstream GitHub repository will this project actually track: `NVIDIA/OpenShell`, `openshell-community`, or both?
2. Should the first validated path be macOS local, Linux local, or a remote Docker host?
3. Will the initial agent target be Codex, Claude Code, OpenCode, or OpenClaw?
4. Do we want this workspace to carry custom policy files from day one, or only after the first sandbox works?

## Sources

- NVIDIA Overview: <https://docs.nvidia.com/openshell/latest/about/overview.html>
- NVIDIA Architecture: <https://docs.nvidia.com/openshell/latest/about/architecture.html>
- NVIDIA Supported Agents: <https://docs.nvidia.com/openshell/latest/about/supported-agents.html>
- NVIDIA Quickstart: <https://docs.nvidia.com/openshell/latest/get-started/quickstart.html>
- NVIDIA Support Matrix: <https://docs.nvidia.com/openshell/latest/reference/support-matrix.html>
- NVIDIA Release Notes Hub: <https://docs.nvidia.com/openshell/latest/about/release-notes.html>
- NVIDIA Launch Blog: <https://developer.nvidia.com/blog/run-autonomous-self-evolving-agents-more-safely-with-nvidia-openshell/>
- GitHub Releases: <https://github.com/NVIDIA/OpenShell/releases>
- PyPI Package: <https://pypi.org/project/openshell/>
