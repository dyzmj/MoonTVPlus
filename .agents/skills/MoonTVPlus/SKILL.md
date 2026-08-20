```markdown
# MoonTVPlus Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill teaches you how to contribute effectively to the MoonTVPlus codebase, a TypeScript project built with Next.js. You'll learn the project's coding conventions, file organization, and the main development workflows for features, UI, admin settings, bugfixes, and releases. This guide also covers how to write and locate tests, and provides handy `/commands` for common tasks.

## Coding Conventions

### File Naming
- **CamelCase** is used for file names.
  - Example: `myComponent.tsx`, `adminSettings.types.ts`

### Import Style
- **Alias imports** are preferred.
  - Example:
    ```typescript
    import { getUser } from '@/lib/user'
    import Settings from '@/components/settingsPanel'
    ```

### Export Style
- **Mixed**: Both default and named exports are used.
  - Example:
    ```typescript
    // Named export
    export function fetchData() { ... }

    // Default export
    export default function AdminPage() { ... }
    ```

### Commit Patterns
- **Freeform** commit messages, often short (average 13 characters).
  - Example: `fix admin bug`, `add TTS`, `update config`

## Workflows

### Feature Development (Multi-file)
**Trigger:** When adding a major new feature or significant enhancement (e.g., TTS for books, short drama features, admin settings).  
**Command:** `/new-feature`

1. Create or update API route files under `src/app/api/...`
2. Update or add relevant component files under `src/components/` or `src/app/[feature]/page.tsx`
3. Update or add supporting library files under `src/lib/`
4. Update configuration files if needed (e.g., `src/lib/config.ts`)
5. Update types if needed (e.g., `src/lib/[feature].types.ts`)
6. Update `package.json` and `pnpm-lock.yaml` if new dependencies are required

**Example:**
```typescript
// src/app/api/tts/route.ts
import { NextResponse } from 'next/server'
import { synthesizeSpeech } from '@/lib/tts'

export async function POST(req: Request) {
  const { text } = await req.json()
  const audio = await synthesizeSpeech(text)
  return NextResponse.json({ audio })
}
```

### Single Component UI Enhancement
**Trigger:** When enhancing or fixing a specific UI component or page.  
**Command:** `/ui-fix`

1. Edit the relevant component or page file under `src/components/` or `src/app/[feature]/page.tsx`
2. Optionally update related CSS or layout files (e.g., `src/app/globals.css`)

**Example:**
```typescript
// src/components/tooltip.tsx
export default function Tooltip({ text }: { text: string }) {
  return <span className="tooltip">{text}</span>
}
```

### Admin Settings Enhancement
**Trigger:** When adding or changing admin panel features or settings.  
**Command:** `/admin-setting`

1. Edit `src/app/admin/page.tsx`
2. Create or update related API route files under `src/app/api/admin/...`
3. Update supporting types/configuration files under `src/lib/`

**Example:**
```typescript
// src/lib/admin.types.ts
export type AdminSettings = {
  theme: string
  notificationsEnabled: boolean
}
```

### Bugfix: Library Vendor (Pancheck)
**Trigger:** When fixing or updating pancheck vendor modules.  
**Command:** `/fix-pancheck`

1. Edit one or more files under `src/lib/pancheck/vendor/checkers/`
2. Optionally update `src/lib/pancheck/index.ts`

**Example:**
```typescript
// src/lib/pancheck/vendor/checkers/exampleChecker.ts
export function checkExample(input: string): boolean {
  return input.startsWith('EXAMPLE')
}
```

### Version Release Update
**Trigger:** When releasing a new version.  
**Command:** `/release`

1. Update `CHANGELOG`
2. Update `VERSION.txt`
3. Update `src/lib/changelog.ts`
4. Update `src/lib/version.ts`

**Example:**
```typescript
// src/lib/version.ts
export const VERSION = '1.2.3'
```

## Testing Patterns

- **Test Framework:** Unknown (not detected in analysis)
- **Test File Pattern:** Files named `*.test.*`
  - Example: `user.test.ts`, `adminPanel.test.tsx`
- **Location:** Typically alongside the code being tested or in the same directory.

**Example:**
```typescript
// src/lib/user.test.ts
import { getUser } from './user'

test('getUser returns user data', () => {
  expect(getUser('alice')).toEqual({ name: 'Alice' })
})
```

## Commands

| Command         | Purpose                                            |
|-----------------|---------------------------------------------------|
| /new-feature    | Start a new multi-file feature or enhancement     |
| /ui-fix         | Make a UI improvement or bugfix                   |
| /admin-setting  | Add or update admin panel features/settings       |
| /fix-pancheck   | Fix bugs in pancheck vendor modules               |
| /release        | Perform a version release update                  |
```