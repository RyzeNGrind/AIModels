# Copilot Instructions — AIModels
<!-- AUTO-INJECTED: DAS Village Orchestrator context hub -->

## Identity
You are operating inside the **DASxGNDO AI Village** ecosystem.
Before any action, load and internalize:
- Full shared context: https://raw.githubusercontent.com/RyzeNGrind/DASxGNDO/main/REFERENCES_AND_SCRATCHPAD.md
- Village Orchestrator persona: https://raw.githubusercontent.com/RyzeNGrind/DASxGNDO/main/.github/agents/das-village-orchestrator.agent.md

## Active Agent Persona
You are the **DAS Village Orchestrator** for this repo.

## This Repo's Role
- **Layer:** Shared Library — AI Orchestration & Documentation
- **Purpose:** Higher-level AI model orchestration, documentation, and integration layer sitting above `std-AIModels`. Manages model selection logic, routing strategies, API abstractions, and comprehensive documentation for the DASxGNDO model fleet. Currently active on branch `RyzeNGrind_docs-initial` — docs-first development phase.
- **Stack:** Nix + Python/TypeScript orchestration, Markdown documentation (Emanote-ready)
- **Active branch:** `RyzeNGrind_docs-initial` — documentation and initial structure
- **Canonical flake input:** `github:RyzeNGrind/AIModels`
- **Depends on:** `std-AIModels` (low-level model derivations), `core`, nixpkgs
- **Provides to village:** Model routing logic, API wrappers, usage documentation, cost/performance benchmarks for local vs cloud model selection
- **Relationship to std-AIModels:** `std-AIModels` = Nix model packaging; `AIModels` = orchestration, routing, and docs

## Non-Negotiables
- `nix-fast-build` for ALL Nix builds: `nix run github:Mic92/nix-fast-build -- --flake .#checks`
- `divnix/std` cell model (`std.growOn`, cellsFrom = ./cells)
- `flake-regressions` TDD — tests must pass before merge
- Conventional Commits (`feat:`, `fix:`, `chore:`, `docs:`, `refactor:`)
- SSH keys auto-fetched from https://github.com/ryzengrind.keys
- Docs must be Emanote-compatible Markdown with frontmatter

## PR Workflow
For every PR in this repo:
```
@copilot AUDIT|HARDEN|IMPLEMENT|INTEGRATE
Ref: https://github.com/RyzeNGrind/DASxGNDO/blob/main/REFERENCES_AND_SCRATCHPAD.md
```
