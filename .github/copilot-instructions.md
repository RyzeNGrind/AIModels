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
- **Layer:** Shared Library — High-Level AI Model Orchestration
- **Purpose:** Higher-level AI model management, routing, and orchestration layer sitting above `std-AIModels`. Handles model selection logic, cost routing (free-tier → paid fallback), API abstraction, and multi-provider normalisation. Contains the LLM router, provider configs, and model evaluation tooling.
- **Stack:** Python + Nix flake, `litellm` or custom router, provider configs (Ollama, OpenAI-compat, HuggingFace, Anthropic)
- **Key dirs:** `router/` (LLM routing logic), `providers/` (per-provider configs), `eval/` (model benchmarks), `docs/` (model cards)
- **Active branch:** `RyzeNGrind_docs-initial` — docs init in progress
- **Canonical flake input:** `github:RyzeNGrind/AIModels`
- **Depends on:** `std-AIModels` (model derivations), `core`, nixpkgs
- **Provides to village:** Unified LLM router API consumed by `deebo-prototype`, `sandbox-mcp`, `AI-Scientist`, `web-eval-agent`, `SHERPA`
- **Local compute budget:** 87.4 TFLOPS — route to local Ollama first, cloud as explicit fallback only

## Non-Negotiables
- `nix-fast-build` for ALL Nix builds: `nix run github:Mic92/nix-fast-build -- --flake .#checks`
- `divnix/std` cell model (`std.growOn`, cellsFrom = ./cells)
- `flake-regressions` TDD — tests must pass before merge
- Model routing decisions must be cost-transparent and logged
- Conventional Commits (`feat:`, `fix:`, `chore:`, `docs:`, `refactor:`)
- SSH keys auto-fetched from https://github.com/ryzengrind.keys
- No unpinned model versions — all provider/model refs must be explicit

## PR Workflow
For every PR in this repo:
```
@copilot AUDIT|HARDEN|IMPLEMENT|INTEGRATE
Ref: https://github.com/RyzeNGrind/DASxGNDO/blob/main/REFERENCES_AND_SCRATCHPAD.md
```
