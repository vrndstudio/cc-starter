# [ name ]

<!-- 1 liner what this project is -->

**Goals**:
- 

## Tech stack
<!-- assuming this is a Next.js project -->

- 

## Pages
- 

## CMS & API Integration

<!-- list schemas, endpoints, etc. -->

## App Router structure

```
...
```

## Design language

[DESIGN.md](docs/DESIGN.md) details design patterns

## Code and component conventions

[CODE.md](docs/CODE.md) details specs for reusable components development and general code conventions.

## Performance baseline

- Lighthouse perf ≥ 95 on every page
- Core Web Vitals green (LCP, INP, CLS)
- `next/image` everywhere — never raw `<img>` except SVGs and decorative
- `next/font`, variable fonts, preload critical weights only
- Bundle: check with `@next/bundle-analyzer` before shipping
- Hero canvas lazy-mounts — never the LCP element
## Accessibility baseline
- WCAG AA minimum
- Colour contrast checked across the brutalist palette
- All interactive elements keyboard-reachable
- `prefers-reduced-motion` disables shader motion, layout animations, parallax
- Hero shader has a static fallback for screen readers and no-JS
- Focus states visible and on-brand

## Development workflow

This defines the agent-human collaboration flow for optimal development experience, splitting responsibilities and optimising tokens cost.

Claude may ask to use `agent-browser` CLI to drive browser checks. Don't use Playwright. otherwise:

**Human runs:**

- `pnpm dev` — long-running dev server; human keeps it open during UI work
- `pnpm build` — production build smoke test
- Browser smoke tests — visual checks, console inspection, theme toggle, navigation
- Prompts Claude back

**Claude runs directly:**

- `pnpm typecheck` — TypeScript strict check
- `pnpm lint` — oxlint
- `pnpm test` — Vitest suite

### Skills

- **Always use the `frontend-design` skill** for any task involving HTML, CSS, JavaScript, React, Vue, components, pages, layouts, or styling. This is non-negotiable, even for small edits.
- **Use the `superpowers:using-superpowers` skill as the default development flow** for any non-trivial work (new features, refactors, anything spanning more than a single file). It orchestrates brainstorming → plan → subagent-driven execution with review. Skip it for one-line fixes, typos, or pure questions.

### Bash Commands

When inspecting git state, run read-only commands (`status`, `log`, `diff`, `rev-parse`, `branch --show-current`) as separate Bash calls. Never chain them with `&&` — the allowlist matches single commands, so chains always prompt. Reserve `&&` for ordering dependencies (e.g. `mkdir x && cd x`).

### Diagnostics

Ignore cSpell warnings entirely. Do not fix spelling in code, comments, or commit messages based on cSpell diagnostics. Only act on diagnostics from the language server (TypeScript, ESLint, etc.).

## Out of scope

<!-- What this project does NOT do, to prevent scope drift. -->

---

## Work-in-progress notes
...


