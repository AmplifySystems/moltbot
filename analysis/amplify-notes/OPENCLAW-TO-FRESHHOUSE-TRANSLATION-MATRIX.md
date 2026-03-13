---
title: OpenClaw to FreshHouse Translation Matrix (filled)
status: active
updated: '2026-03-13'
---

# OpenClaw to FreshHouse Translation Matrix

| OpenClaw concept | Where found in OpenClaw | FreshHouse equivalent | Decision | Notes |
|---|---|---|---|---|
| SOUL.md | docs/reference/templates/SOUL.md; src/agents/workspace.ts (DEFAULT_SOUL_FILENAME, loadTemplate); Project Context | quan/soul.md, sky-fresh-singh/SOUL.md | adapt | Identity by contract from known paths |
| Identity companion docs | IDENTITY.md, USER.md in templates | *-LINGUISTICS-CANONICAL.md | adapt | Canonical language via runtime contract |
| Prompt assembly order | workspace.ts load order AGENTS→SOUL→TOOLS→IDENTITY→USER→HEARTBEAT→BOOTSTRAP→MEMORY; system-prompt.ts Project Context | RUNTIME-PROMPT-CONTRACTS | adopt | Deterministic order |
| Bootstrap workspace files | workspace.ts ensureAgentWorkspace, VALID_BOOTSTRAP_NAMES; workspace-templates.ts | Docs + PM indexes | adapt | No 1:1 replication |
| Tool trust boundaries | system-prompt.ts Safety; security/audit-extra.async.ts; dangerous-config-flags.ts | FreshHouse protocol/rules | adopt | Evidence-first |

Full findings: FreshHouse-Network 0_amplify-systems/docs/implementation/OPENCLAW-FINDINGS.md