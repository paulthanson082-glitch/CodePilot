<img src="docs/icon-readme.png" width="32" height="32" alt="CodePilot" style="vertical-align: middle; margin-right: 8px;" /> CodePilot
===

**An iPad-friendly toolbox for developers and power users** -- clean up text, format and validate JSON, copy/share results instantly, and more. Built with an iPad-first UX philosophy so every tool works beautifully on a touchscreen as well as a desktop.

[![GitHub release](https://img.shields.io/github/v/release/op7418/CodePilot)](https://github.com/op7418/CodePilot/releases)
[![Platform](https://img.shields.io/badge/platform-macOS%20%7C%20Windows-lightgrey)](https://github.com/op7418/CodePilot/releases)
[![License](https://img.shields.io/badge/license-MIT-blue)](LICENSE)

[中文文档](./README_CN.md)

---

## MVP Features

1. **🏠 Toolbox Home** -- A clean launchpad that lists all available tools. Tap or click any tile to open a tool instantly.
2. **✏️ Text Cleanup Tool** -- Trim whitespace, normalise line endings, remove duplicate lines, and apply common text transforms with a single tap.
3. **📋 JSON Formatter + Validator** -- Paste raw JSON, get it pretty-printed and validated in real time; errors are highlighted with clear messages.
4. **⚡ Copy / Share Quick Actions** -- One-tap copy to clipboard and native share sheet integration so results flow straight to other apps.
5. **📖 Basic Docs and Roadmap** -- In-app documentation and a visible roadmap so users always know what is coming next.

> See [`docs/roadmap.md`](docs/roadmap.md) for the full phased plan.

---

## Screenshots

![CodePilot](docs/screenshot.png)

---

## Prerequisites

> **Important**: CodePilot calls the Claude Code Agent SDK under the hood. Make sure `claude` is available on your `PATH` and that you have authenticated (`claude login`) before launching the app.

| Requirement | Minimum version |
|---|---|
| **Node.js** | 18+ |
| **Claude Code CLI** | Installed and authenticated (`claude --version` should work) |
| **npm** | 9+ (ships with Node 18) |

---

## Download

Pre-built releases are available on the [**Releases**](https://github.com/op7418/CodePilot/releases) page.

### Supported Platforms

- **macOS**: Universal binary (arm64 + x64) distributed as `.dmg`
- **Windows**: x64 distributed as `.zip`

> Linux builds are planned. Contributions welcome.

---

## Getting Started

```bash
# 1. Clone the repository
git clone https://github.com/paulthanson082-glitch/CodePilot.git
cd CodePilot

# 2. Install dependencies
npm install

# 3. Start in development mode (browser)
npm run dev

# 4. Or start the full Electron app in dev mode
npm run electron:dev
```

Then open [http://localhost:3000](http://localhost:3000) in your browser (dev mode) or wait for the Electron window to appear.

### Git Workflow

We follow a simple feature-branch workflow:

1. **Create a feature branch** from `main`:
   ```bash
   git checkout main && git pull
   git checkout -b feature/your-feature-name
   ```
2. **Make focused commits** using [Conventional Commits](https://www.conventionalcommits.org/) style:
   - `feat:` for new features
   - `fix:` for bug fixes
   - `docs:` for documentation changes
   - `chore:` for maintenance tasks
3. **Push and open a PR** against `main`. Keep PRs small and focused -- one feature or fix per PR.
4. **Lint before pushing**: `npm run lint`

### iPad Setup

For tips on using CodePilot and running an iPad-focused development workflow, see [`docs/ipad-setup.md`](docs/ipad-setup.md).

---

## Installation Troubleshooting

CodePilot is not code-signed yet, so your operating system will display a security warning the first time you open it.

### macOS

You will see a dialog that says **"Apple cannot check it for malicious software"**.

**Option 1 -- Right-click to open**

1. Right-click (or Control-click) `CodePilot.app` in Finder.
2. Select **Open** from the context menu.
3. Click **Open** in the confirmation dialog.

**Option 2 -- System Settings**

1. Open **System Settings** > **Privacy & Security**.
2. Scroll down to the **Security** section.
3. You will see a message about CodePilot being blocked. Click **Open Anyway**.
4. Authenticate if prompted, then launch the app.

**Option 3 -- Terminal command**

```bash
xattr -cr /Applications/CodePilot.app
```

This strips the quarantine attribute so macOS will no longer block the app.

### Windows

Windows SmartScreen will block the installer or executable.

**Option 1 -- Run anyway**

1. On the SmartScreen dialog, click **More info**.
2. Click **Run anyway**.

**Option 2 -- Disable App Install Control**

1. Open **Settings** > **Apps** > **Advanced app settings**.
2. Toggle **App Install Control** (or "Choose where to get apps") to allow apps from anywhere.

---

## Tech Stack

| Layer | Technology |
|---|---|
| Framework | [Next.js 16](https://nextjs.org/) (App Router) |
| Desktop shell | [Electron 40](https://www.electronjs.org/) |
| UI components | [Radix UI](https://www.radix-ui.com/) + [shadcn/ui](https://ui.shadcn.com/) |
| Styling | [Tailwind CSS 4](https://tailwindcss.com/) |
| Animation | [Motion](https://motion.dev/) (Framer Motion) |
| AI integration | [Claude Agent SDK](https://www.npmjs.com/package/@anthropic-ai/claude-agent-sdk) |
| Database | [better-sqlite3](https://github.com/WiseLibs/better-sqlite3) (embedded, per-user) |
| Markdown | react-markdown + remark-gfm + rehype-raw + [Shiki](https://shiki.style/) |
| Streaming | [Vercel AI SDK](https://sdk.vercel.ai/) helpers + Server-Sent Events |
| Icons | [Hugeicons](https://hugeicons.com/) + [Lucide](https://lucide.dev/) |
| Testing | [Playwright](https://playwright.dev/) |
| Build / Pack | electron-builder + esbuild |

---

## Project Structure

```
CodePilot/
├── docs/                        # Documentation
│   ├── roadmap.md               # Phased development roadmap
│   └── ipad-setup.md            # iPad productivity setup guide
├── src/
│   ├── core/                    # Shared utilities, helpers, and core logic
│   ├── ui/                      # Reusable UI components (iPad-first)
│   ├── tools/
│   │   ├── text/                # Text Cleanup Tool
│   │   ├── dev/                 # Developer tools (JSON formatter, etc.)
│   │   └── productivity/        # Productivity-focused tools
│   ├── app/                     # Next.js App Router pages & API routes
│   ├── components/              # Shared React components
│   ├── hooks/                   # Custom React hooks
│   ├── lib/                     # Core library code
│   └── types/                   # TypeScript interfaces & contracts
├── tests/                       # Unit and integration tests
├── electron/                    # Electron main process & preload
├── public/                      # Static assets
├── scripts/                     # Build and packaging scripts
├── package.json
└── tsconfig.json
```

---

## Development

```bash
# Run Next.js dev server only (opens in browser)
npm run dev

# Run the full Electron app in dev mode
# (starts Next.js + waits for it, then opens Electron)
npm run electron:dev

# Production build (Next.js static export)
npm run build

# Build Electron distributable + Next.js
npm run electron:build

# Package macOS DMG (universal binary)
npm run electron:pack
```

### Notes

- The Electron main process (`electron/main.ts`) forks the Next.js standalone server and connects to it over `127.0.0.1` with a random free port.
- Chat data is stored in `~/.codepilot/codepilot.db` (or `./data/codepilot.db` in dev mode).
- The app uses WAL mode for SQLite, so concurrent reads are fast.

---

## Contributing

Contributions are welcome! To get started:

1. Fork the repository and create a feature branch off `main`.
2. Install dependencies with `npm install`.
3. Run `npm run electron:dev` (or `npm run dev`) to test your changes locally.
4. Make sure `npm run lint` passes before opening a pull request.
5. Open a PR against `main` with a clear description of what changed and why.

See the [roadmap](docs/roadmap.md) for planned features -- feel free to pick up anything in Phase 2 or Phase 3.

---

## License

MIT
