# iPad Productivity Setup for CodePilot

This guide covers how to set up your iPad for a focused, productive development and toolbox workflow with CodePilot.

---

## Focus Modes

Use iPadOS **Focus** modes to minimise distractions while working.

1. **Create a "Dev" Focus** (`Settings → Focus → +`).
2. Allow only the apps you need: CodePilot, Files, Safari (docs), and your terminal app (e.g. Working Copy or SSH client).
3. Enable **Focus Status** so messaging apps show "Do Not Disturb" automatically.
4. Assign the Focus to a **Home Screen page** dedicated to development tools — only your dev apps appear on that page.
5. Set up an **automation**: turn the Focus on automatically when you open CodePilot (`Shortcuts → Automation → App → Open`).

---

## Core Apps

| App | Purpose |
|-----|---------|
| **CodePilot** | Main toolbox |
| **Working Copy** | Git client with Files.app integration |
| **Runestone** | Lightweight code/text editor |
| **Safari** | Documentation and web research |
| **Toolbox for Git** (optional) | Visual branch/history browser |
| **Scriptable** | JavaScript automation and quick scripts |
| **Shortcuts** | Glue between apps; invoke CodePilot tools from anywhere |

---

## Essential Shortcuts

### System shortcuts (iPad)

| Shortcut | Action |
|----------|--------|
| `⌘ Space` | Spotlight Search — open any app instantly |
| `⌘ Tab` | App switcher |
| `⌘ H` | Go to Home Screen |
| `⌘ .` | Cancel / dismiss |
| `Globe + ↓` | Show / hide keyboard |

### Inside CodePilot

| Shortcut | Action |
|----------|--------|
| `⌘ V` | Paste into active tool input |
| `⌘ C` | Copy tool output |
| `⌘ K` | Clear / reset current tool |
| `⌘ F` | Focus search on Toolbox Home |
| `⌘ ,` | Open Settings |

> **Tip**: Pair a Magic Keyboard or Smart Keyboard Folio to unlock all keyboard shortcuts. Most tap actions have a keyboard equivalent.

---

## Multitasking Setup

iPadOS Split View and Slide Over let you run CodePilot alongside other apps without switching.

- **Split View** (50/50 or 70/30): drag CodePilot and your editor/terminal side by side.
- **Slide Over**: pin a lightweight reference app (e.g. a browser with docs) as a Slide Over panel on top of CodePilot.
- **Stage Manager** (iPad Pro / Air M1+): arrange CodePilot and up to three other windows on screen simultaneously.

---

## Workflow

### Typical text-cleanup workflow

1. Copy text from any app (email, note, document).
2. Switch to CodePilot → **Text Cleanup Tool**.
3. `⌘ V` to paste.
4. Tap the desired transform (e.g. *Trim whitespace*, *Remove duplicate lines*).
5. `⌘ C` or tap **Copy** to copy the result back to clipboard.
6. Switch back to the source app and paste.

### Typical JSON workflow

1. Copy raw JSON from a browser, API response, or log file.
2. Switch to CodePilot → **JSON Formatter**.
3. `⌘ V` to paste.
4. Errors are highlighted immediately; fix them inline or in your source.
5. Tap **Format** to pretty-print.
6. Use **Share** to send the formatted JSON to Files, Mail, or another app.

### Git workflow with Working Copy

1. Clone your repository in Working Copy.
2. Create a feature branch (`feature/your-change`).
3. Edit files in Runestone or another editor via the Files integration.
4. Switch to CodePilot to validate or clean up any JSON / text files your change touches.
5. Commit and push from Working Copy.
6. Open a PR in Safari (GitHub mobile site or desktop mode).

---

## Tips and Tricks

- **Back Tap**: assign *Copy* or *Paste* to a double or triple back-tap (`Settings → Accessibility → Touch → Back Tap`) for even faster clipboard access.
- **Text Replacement**: add common JSON snippets or boilerplate in `Settings → General → Keyboard → Text Replacement` so you can type short abbreviations and get a full template.
- **Drag and Drop**: on iPadOS you can drag text from any app directly into a CodePilot tool input — no clipboard step needed.
- **Quick Note**: use the system Quick Note (swipe from bottom-right corner with Apple Pencil or four-finger swipe) to jot down ideas without leaving CodePilot.

---

*For the full feature roadmap see [`roadmap.md`](roadmap.md).*
