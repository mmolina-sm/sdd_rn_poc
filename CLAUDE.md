# AI-DLC and Spec-Driven Development

Spec-Driven Development implementation on AI-DLC (AI Development Life Cycle)

## Project Context

### Paths
- Steering: `.kiro/steering/`
- Specs: `.specify/` (SpecKit features)
- Specs (cc-sdd): `.kiro/specs/` (supplementary)

### Layers

**SpecKit** (`/speckit.*`) — Primary tool for Phases 1-3: specification, planning, task generation
**cc-sdd** (`/kiro:*`) — Supplementary commands for steering, validation, and gap analysis
**Beads** (`bd`) — Phase 4 issue tracking and execution
**VibeKanban** — Visual board and parallel agent orchestration

### Active Specifications
- Check `.specify/` for active SpecKit features
- Use `/speckit.analyze` or `specify check` to review status

## Development Guidelines
- Think in English, generate responses in English. All Markdown content written to project files (e.g., requirements.md, design.md, tasks.md, research.md, validation reports) MUST be written in the target language configured for this specification (see spec.json.language).

## Full AI-DLC Pipeline

### Phase 0 — Foundation (one-time)
```
/speckit.constitution                   # Establish architectural principles
/kiro:steering                          # Bootstrap project context (cc-sdd)
```

### Phases 1-3 — Intent (per feature, SpecKit primary)
```
/speckit.specify "description"          # Create/update feature specification
/speckit.plan {feature}                 # Technical design and planning
/speckit.tasks {feature}                # Generate implementation tasks
```

### Bridge — Tasks to Issues
```
/speckit.taskstoissues {feature}        # Convert tasks.md → Beads issues
```

### Phase 4 — Execution
```
bd ready                                # Find unblocked tasks
/speckit.implement {feature}            # Implement tasks
bd close <id>                           # Mark task done
```

### Visual Board
```
npx vibe-kanban                         # Launch Kanban board
```

### Validation & Quality (optional, any phase)
- `/speckit.analyze` — cross-artifact consistency analysis
- `/speckit.checklist` — requirements quality checklist
- `/speckit.clarify` — de-risk ambiguous areas
- `/kiro:validate-gap {feature}` — gap analysis (cc-sdd)
- `/kiro:validate-design {feature}` — design review (cc-sdd)
- `/kiro:validate-impl {feature}` — implementation verification (cc-sdd)
- `/kiro:spec-status {feature}` — progress check (cc-sdd)

## Development Rules
- 3-phase approval workflow: Specify → Plan → Tasks → Implement
- Human review required each phase
- SpecKit commands are the primary workflow; cc-sdd (`/kiro:*`) commands are supplementary
- Follow the user's instructions precisely, and within that scope act autonomously: gather the necessary context and complete the requested work end-to-end in this run, asking questions only when essential information is missing or the instructions are critically ambiguous.

## Steering Configuration
- Load entire `.kiro/steering/` as project memory
- Default files: `product.md`, `tech.md`, `structure.md`
- Custom files are supported (managed via `/kiro:steering-custom`)


<!-- BEGIN BEADS INTEGRATION v:1 profile:minimal hash:b9766037 -->
## Beads Issue Tracker

This project uses **bd (beads)** for issue tracking. Run `bd prime` to see full workflow context and commands.

### Quick Reference

```bash
bd ready              # Find available work
bd show <id>          # View issue details
bd update <id> --claim  # Claim work
bd close <id>         # Complete work
```

### Rules

- Use `bd` for ALL task tracking — do NOT use TodoWrite, TaskCreate, or markdown TODO lists
- Run `bd prime` for detailed command reference and session close protocol
- Use `bd remember` for persistent knowledge — do NOT use MEMORY.md files

## Landing the Plane (Session Completion)

**When ending a work session**, you MUST complete ALL steps below. Work is NOT complete until `git push` succeeds.

**MANDATORY WORKFLOW:**

1. **File issues for remaining work** - Create issues for anything that needs follow-up
2. **Run quality gates** (if code changed) - Tests, linters, builds
3. **Update issue status** - Close finished work, update in-progress items
4. **PUSH TO REMOTE** - This is MANDATORY:
   ```bash
   git pull --rebase
   bd dolt push
   git push
   git status  # MUST show "up to date with origin"
   ```
5. **Clean up** - Clear stashes, prune remote branches
6. **Verify** - All changes committed AND pushed
7. **Hand off** - Provide context for next session

**CRITICAL RULES:**
- Work is NOT complete until `git push` succeeds
- NEVER stop before pushing - that leaves work stranded locally
- NEVER say "ready to push when you are" - YOU must push
- If push fails, resolve and retry until it succeeds
<!-- END BEADS INTEGRATION -->

## Active Technologies
- TypeScript 5.9 (strict mode) + Expo 54, React Native 0.81.5, React 19.1, Expo Router 6, expo-secure-store (new) (001-login-access-control)
- expo-secure-store (session token + user data on device) (001-login-access-control)

## Recent Changes
- 001-login-access-control: Added TypeScript 5.9 (strict mode) + Expo 54, React Native 0.81.5, React 19.1, Expo Router 6, expo-secure-store (new)
