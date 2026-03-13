---
title: OpenClaw Analysis Intake Checklist
status: active
updated: '2026-03-13'
---

# OpenClaw Analysis Intake Checklist

Use this checklist before translating any pattern into FreshHouse operations.

**Completed scan (2026-03-13):** Full findings in FreshHouse-Network: `0_amplify-systems/docs/implementation/OPENCLAW-FINDINGS.md`.

## 1) Identity/bootstrap system

- [x] Locate where `SOUL.md` is created/loaded. → `docs/reference/templates/SOUL.md`; `src/agents/workspace.ts` (loadTemplate, writeFileIfMissing).
- [x] Document runtime injection order for identity files. → AGENTS → SOUL → TOOLS → IDENTITY → USER → HEARTBEAT → BOOTSTRAP → MEMORY.
- [x] Confirm fallback behavior when soul files are missing. → `[MISSING] Expected at: <path>` in Project Context.

## 2) Prompt/runtime contract

- [x] Identify system prompt assembly logic. → `src/agents/system-prompt.ts`; Project Context after Tooling/Safety/Workspace.
- [x] Capture deterministic ordering and priority rules. → Fixed order in loadWorkspaceBootstrapFiles + buildBootstrapContextFiles.
- [x] Note anti-drift mechanisms. → "If SOUL.md is present, embody its persona"; safety rule against changing system prompts.

## 3) Memory and context

- [x] Identify persistent memory layers. → MEMORY.md + memory/*.md; memory_search/memory_get.
- [x] Document workspace/project context loading rules. → Session store + transcript jsonl; docs/reference/session-management-compaction.md.
- [x] Record any summarization/compaction behaviors. → Auto-compaction; pi-extensions/compaction-safeguard.

## 4) Tooling and trust boundaries

- [x] Document tool allow/deny model. → Per-agent, per-session; minimal bootstrap for subagent/cron.
- [x] Capture safety boundary patterns. → Safety section in system-prompt.ts; tools.fs.workspaceOnly; audit-extra.async.
- [x] Identify where claims are gated by tool evidence. → Safety + no self-preservation/replication; evidence-first.

## 5) Operational mapping to FreshHouse

- [x] Map pattern to Quan operation. → OPENCLAW-FINDINGS §6; RUNTIME-PROMPT-CONTRACTS.
- [x] Map pattern to Sky Fresh Singh operation. → Same contract; SOUL + linguistics.
- [x] Decide adopt / adapt / reject with rationale. → OPENCLAW-TO-FRESHHOUSE-TRANSLATION-MATRIX.md.

## 6) Export discipline

- [x] Convert findings into markdown docs only. → OPENCLAW-FINDINGS.md in FreshHouse.
- [x] Copy only finalized docs into FreshHouse repo. → Done.
- [x] Add links in Mermaid/implementation indexes. → MERMAID-DIAGRAMS-INDEX; OPENCLAW-SOUL-FILES doc §10.
