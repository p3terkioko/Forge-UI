# AI Coding Agents — Forge Frontend

All AI tools are welcome and encouraged on this project. Every AI tool is held to the same standard as human-written code — it goes through the same PR review and must pass lint and typecheck before merge.

This file documents which configuration file each tool reads, and how to invoke it correctly for this project.

---

## Claude Code

**Config file:** `CLAUDE.md` (loaded automatically)

**How to invoke:**
```bash
claude
```

Claude Code reads `CLAUDE.md` automatically when opened in this directory. No manual briefing needed. It knows the stack, what is already built, and the full set of conventions.

---

## GitHub Copilot

**Config file:** `.github/copilot-instructions.md` (loaded automatically in VS Code and JetBrains)

**How to invoke:**
Use Copilot Chat or inline completions as normal. The instructions file is picked up automatically in any workspace-aware Copilot session. To ask Copilot a question about this project, open Copilot Chat and ask directly — it will apply the workspace instructions.

No manual briefing needed as long as you are working inside this repository.

---

## Cursor

**Config file:** `.cursor/rules/forge.mdc` (applied automatically to all `src/**/*.ts` and `src/**/*.tsx` files)

**How to invoke:**
Open this repository in Cursor. The rule file is applied automatically via the `.cursor/rules/` directory. Use Cursor Chat (`Cmd+L` / `Ctrl+L`) or inline generation as normal.

To verify the rule is active: open Cursor Chat and ask "What are the Forge conventions?" — it should describe the rules without you pasting them.

---

## Windsurf (Codeium)

**Config file:** `.windsurfrules` (loaded automatically)

**How to invoke:**
Open this repository in Windsurf. The `.windsurfrules` file is picked up automatically. Use Cascade or inline completions as normal.

---

## Aider

**Config file:** `CONVENTIONS.md` (Aider reads this automatically on startup)

**How to invoke:**
```bash
aider --model gpt-4o   # or your preferred model
```

Aider reads `CONVENTIONS.md` automatically when present in the working directory. The file contains the condensed rules Aider needs. The full rules are in `CONVECTIONS.md`.

Recommended flags for this project:
```bash
aider --model gpt-4o --no-auto-commits --watch-files
```

---

## Rules that apply to all agents

Regardless of which tool generated the code, the following apply before any PR is opened:

- `npm run lint` passes with zero errors
- `npm run typecheck` passes with zero errors
- No `any` types introduced
- No hardcoded hex or pixel values introduced
- No `fetch()` calls outside `src/lib/api.ts`
- No business logic inside a component — hooks only
- No duplicate components — check `src/components/README.md` first
- Every new component has a `.stories.tsx` file

AI-generated code that violates any of these will be rejected in review, same as human-written code.
