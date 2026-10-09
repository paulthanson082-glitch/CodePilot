# CodePilot Roadmap

This document outlines the planned development phases for CodePilot. Checked items are complete or in progress; unchecked items are planned.

---

## Phase 1 — MVP (current focus)

> Goal: ship a lean, polished toolbox that works flawlessly on iPad and desktop.

- [ ] **Toolbox Home** — clean grid/list of all available tools with search/filter
- [ ] **Text Cleanup Tool** — trim whitespace, normalise line endings, remove duplicate lines, change case
- [ ] **JSON Formatter + Validator** — pretty-print JSON, validate structure, highlight errors inline
- [ ] **Copy / Share quick actions** — one-tap copy to clipboard and native share sheet on every tool output
- [ ] **Unit tests** for core transform functions (`tests/`)
- [x] **Docs and roadmap** — README, roadmap, iPad setup guide (`docs/`)

### Quality targets for Phase 1

- **Speed**: every tool transform completes in < 100 ms on a 1 MB input.
- **Predictable transforms**: given the same input the output is always identical (pure functions, no hidden state).
- **iPad-first UX**: tap targets ≥ 44 × 44 pt, no hover-only interactions, keyboard toolbar support on iPadOS.

---

## Phase 2 — Growth

> Goal: expand the toolset and improve sharing / collaboration.

- [ ] **Base64 encode / decode**
- [ ] **URL encode / decode**
- [ ] **Markdown preview** — live render with copy-as-HTML output
- [ ] **Diff viewer** — side-by-side or inline diff between two text inputs
- [ ] **Colour picker** — hex/RGB/HSL converter with clipboard integration
- [ ] **History** — remember the last N inputs per tool across app restarts (local storage)
- [ ] **Favourites / pinning** — let users pin their most-used tools to the top of the home grid
- [ ] **Dark / Light theme toggle**

---

## Phase 3 — Power Features

> Goal: power-user and developer-focused additions.

- [ ] **Custom transforms** — let users write simple JavaScript snippets as personal tools
- [ ] **Batch processing** — drag-and-drop multiple files and apply a tool to all of them
- [ ] **iCloud / Files integration** — open from and save to Files.app on iPadOS
- [ ] **Shortcuts (Siri/Shortcuts app) actions** — expose tools as Shortcuts actions for automation
- [ ] **Accessibility audit pass** — VoiceOver, Dynamic Type, and Reduce Motion compliance
- [ ] **Localisation** — at least English and Simplified Chinese (`i18n`)

---

*Last updated: 2026-03-07*
