# OpenShell Local Lab

Research-first scaffold for evaluating and integrating NVIDIA OpenShell locally.

## Status

As of 2026-03-18 this workspace contains only documentation and project structure.

Not done yet:

- Install the OpenShell CLI
- Pull container images
- Clone the upstream NVIDIA repository
- Initialize local Git metadata
- Attach a remote GitHub repository
- Run any sandbox, gateway, or provider command

## Current Goal

Build a clean project foundation for a larger OpenShell-based effort without downloading or executing anything yet.

## Working Assumptions

- The upstream GitHub repository will be provided later.
- Initial work is local-first, with deployment planning after the local path is clearer.
- Docker Desktop is the first likely runtime dependency for local evaluation.
- This workspace is a consumer/integration project, not a mirror of NVIDIA's upstream repository.

## Current Research Snapshot

- NVIDIA describes OpenShell as an open-source runtime for autonomous AI agents with sandboxed execution and policy-driven controls.
- NVIDIA officially announced OpenShell on 2026-03-16 as part of the NemoClaw stack.
- The public GitHub repository shows very fast release movement; the latest visible release is `v0.0.10` dated 2026-03-18.
- Host support is strongest on Debian/Ubuntu and macOS Apple Silicon via Docker Desktop. Windows via WSL2 is marked experimental.
- Codex support appears documented inconsistently across official pages, so that path should be treated as a validation item instead of an assumption.
- Generic web searches for "NVIDIA OpenShell" can also surface older NVIDIA networking material about an `OPEN_SHELL` preboot behavior. For this project, the source of truth is the AI-agent runtime at `docs.nvidia.com/openshell` and `github.com/NVIDIA/OpenShell`.

See:

- [docs/research/2026-03-18-openshell-official.md](/Users/denniswestermann/Library/Mobile Documents/com~apple~CloudDocs/Desktop/Coding Projekte/OpenShell/docs/research/2026-03-18-openshell-official.md)
- [docs/research/2026-03-18-openshell-community.md](/Users/denniswestermann/Library/Mobile Documents/com~apple~CloudDocs/Desktop/Coding Projekte/OpenShell/docs/research/2026-03-18-openshell-community.md)

## Project Layout

- `docs/research/`: dated source-based research notes
- `docs/architecture/`: project architecture notes and target topologies
- `docs/decisions/`: ADR-style decision log
- `plans/`: roadmap and execution planning
- `sandbox/policies/`: future local policy files and policy notes
- `sandbox/providers/`: provider and credential strategy notes
- `scripts/`: local helper scripts once the project moves beyond research

## Immediate Next Steps

1. Confirm the target GitHub repository once you provide it.
2. Decide whether the first supported path should be macOS-local, Linux-local, or remote Docker host.
3. Validate one minimal local path before designing the larger deployment shape.
4. Resolve the Codex support mismatch before assuming a Codex-first workflow.
