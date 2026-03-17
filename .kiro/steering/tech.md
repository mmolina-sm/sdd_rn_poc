# Technology Stack

## Runtime & Framework
- **React Native**: 0.81.5 (New Architecture enabled)
- **React**: 19.1.0 (React Compiler enabled)
- **Expo**: 54.0.33 (managed workflow)
- **Expo Router**: 6.0.23 (file-based routing, typed routes)
- **TypeScript**: 5.9.2 (strict mode)

## Navigation & UI
- **@react-navigation/bottom-tabs**: 7.4.0
- **react-native-reanimated**: 4.1.1
- **react-native-gesture-handler**: 2.28.0
- **react-native-screens**: 4.16.0
- **expo-image**: 3.0.11

## Build & Tooling
- **Platform**: iOS, Android, Web (static output)
- **Linting**: ESLint 9.25 with eslint-config-expo
- **Path aliases**: `@/*` → `./*`
- **Experiments**: typed routes, React Compiler

## AI-DLC Toolchain
- **SpecKit**: v0.3.0 — project scaffold, specification workflow
- **cc-sdd (Kiro commands)**: requirements, design, tasks, implementation
- **Beads (bd)**: v0.61.0 — structured issue tracking with Dolt backend
- **VibeKanban**: v0.1.31 — visual Kanban board, parallel agent orchestration
- **Dolt**: SQL database backend for Beads

## Conventions
- Strict TypeScript — no `any`, no implicit returns
- Functional components with hooks
- Expo Router file-based routing conventions
- New Architecture (Fabric, TurboModules) enabled by default
