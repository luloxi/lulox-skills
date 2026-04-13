---
name: midnight-project-building
description: "Build Midnight Network / Compact projects end-to-end with a product-first workflow: repo scaffolding, docs lookup, contract/app architecture, testing, deployment, and iterative improvement. Use when the user wants to start or evolve a Midnight project, or wants a reusable skill for Hermes, Carly, and Sancho Panza."
version: 0.1.0
author: Hermes Agent
license: MIT
metadata:
  hermes:
    tags: [midnight, compact, cardano, input-output, iohk, mcp, github, hackathon, dapp]
---

# Midnight Project Building

Use this skill when building projects on Midnight Network / Compact, especially if the user wants a reusable playbook that can be improved over time and shared across agents.

## Goals
- Help the agent build Midnight projects correctly, quickly, and with good structure.
- Prefer product-shaped scaffolds over tiny demos.
- Keep the skill updated as new discoveries are made.
- Make it usable by Hermes, Carly, Sancho Panza, or any other agent with access to the repo/skills.

## When to use
- The user mentions Midnight Network, Compact, partnerchain/Cardano, or Input Output.
- The user wants a contract, dApp, dashboard, or hackathon scaffold.
- The user wants an MCP-based workflow or live docs lookup.
- The user wants the skill to evolve as the team learns.

## Core workflow

### 1) Clarify the project shape
Before coding, identify:
- product goal
- onchain vs offchain responsibilities
- privacy requirements
- whether the app needs a frontend, backend, or both
- whether the project is local-only, testnet, or public-facing

### 2) Pull live Midnight docs first
Prefer current docs over memory.
Check:
- Midnight docs home
- smart contract docs
- getting started / hello world
- any relevant blog posts about MCP or Compact workflows

Useful queries:
- "Midnight Network Compact docs"
- "Midnight hello world contract"
- "Midnight MCP AI assisted development"

### 3) Decide the architecture
Typical shape:
- contracts: Compact / Midnight logic
- app: frontend and/or backend
- adapter: wallet, signing, attestation, prompt bridge, or event bridge
- docs: protocol explanation, threat model, setup guide
- CI: lint/test/build/deploy

### 4) Scaffold like a real project
Prefer a repo layout such as:

```text
repo/
├── README.md
├── docs/
├── contracts/
├── apps/
├── packages/
├── tests/
└── .github/workflows/
```

### 5) Keep privacy and reveal flow explicit
If the project involves commitments / selective disclosure:
- store commitments onchain
- keep raw data offchain until reveal
- define verification steps clearly
- document what is public, what is private, and what gets revealed later

### 6) Build the UI product-first
If there is a frontend, make it look like a real product:
- clear landing page
- strong copy
- visible state transitions
- dashboard-style status panels
- avoid toy/demo styling when the use case is serious

### 7) Add tests early
Test:
- contract invariants
- adapter event flow
- serialization / hashing
- UI state transitions
- deployment scripts

### 8) Iterate in small steps
After each meaningful change:
- verify it runs
- tighten the README
- record any new knowledge here
- keep examples minimal but accurate

## Suggested commands and research targets
When allowed by the environment, use:
- web search for docs and examples
- GitHub repo inspection for reference implementations
- test-driven development for contract and adapter changes
- GitHub Pages or other lightweight hosting for public demo sites

## Recommended defaults
- Prefer TypeScript for app/adapters unless the repo already uses something else.
- Prefer a minimal, reproducible scaffold.
- Keep secrets out of the repo.
- Keep onchain data minimal.

## Prompt template for Midnight work

"Build this as a real Midnight project: first find the live docs, then define the onchain/offchain split, then scaffold the repo, then implement the smallest working version, then add tests and docs. If the design changes, update this skill with what you learned."

## Maintenance rules
When you learn something durable:
- patch this skill
- add a short pitfall note
- add the exact command or workflow that worked
- keep examples current

## Common pitfalls
- Don’t assume old docs are current.
- Don’t put raw private data onchain.
- Don’t overbuild before the architecture is clear.
- Don’t forget to document the reveal/verification path.
- Don’t let the skill become a generic Midnight summary; keep it action-oriented.

## Improvement loop
After each Midnight project:
1. note what worked
2. note what failed
3. patch this skill
4. if a repeatable workflow emerges, turn it into a sub-skill or template

## Collaboration note
This skill is intended to be shared across agents. If Carly or Sancho Panza discovers a better workflow, update this file so the whole team benefits.
