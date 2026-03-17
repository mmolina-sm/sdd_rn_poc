# Project Structure

## File-Based Routing (Expo Router)
```
app/
├── _layout.tsx          # Root layout (providers, global config)
├── modal.tsx            # Modal route
└── (tabs)/              # Tab navigator group
    ├── _layout.tsx      # Tab bar configuration
    └── [screen].tsx     # Individual tab screens
```

## Component Organization
```
components/
├── [ComponentName].tsx           # Standalone components
├── [ComponentName]/              # Complex components with subparts
│   ├── index.tsx
│   └── [SubComponent].tsx
├── ui/                           # Reusable UI primitives
└── navigation/                   # Navigation-specific components
```

## Supporting Directories
```
assets/                  # Static assets (images, fonts)
constants/               # App-wide constants and theme values
hooks/                   # Custom React hooks
scripts/                 # Build and utility scripts
```

## AI-DLC Directories
```
.kiro/
├── steering/            # Project context (product.md, tech.md, structure.md)
├── settings/            # cc-sdd configuration
└── specs/               # Feature specifications (requirements, design, tasks)

.specify/
├── memory/              # SpecKit memory (constitution.md)
├── templates/           # Specification templates
├── scripts/             # Workflow automation scripts
└── extensions/          # SpecKit extensions

.beads/                  # Beads issue tracker data
├── config.yaml          # Beads configuration
├── hooks/               # Git hooks for Beads
└── issues.jsonl         # Issue data (portable)

.claude/
├── commands/kiro/       # cc-sdd slash commands
└── settings.local.json  # Claude Code local settings (hooks, MCP)
```

## Naming Conventions
- Files: `kebab-case.tsx` for routes, `PascalCase.tsx` for components
- Directories: `kebab-case/` or `(group)/` for route groups
- Path alias: `@/` maps to project root
