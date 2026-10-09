# tests

Unit and integration tests for CodePilot.

## Structure (planned)

```
tests/
├── core/          # Tests for src/core utilities and transforms
├── tools/
│   ├── text/      # Tests for the Text Cleanup Tool
│   └── dev/       # Tests for developer tools (JSON formatter, etc.)
└── ui/            # Component tests
```

## Running tests

```bash
npm test
```

See the root `package.json` for available test scripts.
