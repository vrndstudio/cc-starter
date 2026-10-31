# CC Starter

Bare-bones starting point for a new project on a [dropkit-starter-cc](https://github.com/vrndstudio/dropkit-starter-cc) droplet. Ships a project-scoped `.claude/` config that reduces permission prompts for normal dev-loop commands (`pnpm dev`, `pnpm test`, `pnpm add`, `ncu`, `bun`, etc.) while leaving user-level deny rules and hooks in place.

## Use

```bash
# 1. Clone as your new project (drop the template's git history)
git clone https://github.com/vrndstudio/cc-starter.git my-new-project
cd my-new-project
rm -rf .git && git init

# 2. Scaffold your framework of choice (template is framework-agnostic)
pnpm create next-app . --typescript      # or:
pnpm create vite . --template react-ts   # or any other generator

# 3. Fill in CLAUDE.md with project specifics

# 4. Open Claude Code in this directory and install plugins (below)
```

## Layout

```
.
├── README.md              this file
├── CLAUDE.md              project-scoped context, fill in before first session
├── .claude/
│   ├── settings.json      project-scoped permission allows
│   └── commands/          subset: code-review, test, security-check, update-while-working
├── .gitignore             node defaults + .env*
└── .editorconfig          2-space, LF, UTF-8
```

User-level config (`~/.claude/settings.json`, `~/.claude/CLAUDE.md`, hooks) provided by `dropkit-starter-cc` still applies. Project settings only **add** allows; deny rules and hooks (rm -rf block, push-to-main block) stay enforced.

## Plugins

Paste the following slash commands inside a Claude Code session in this directory.

### Anthropic official

```
/plugin marketplace add anthropics/skills
```

```
/plugin install superpowers@claude-plugins-official
/plugin install skill-creator@claude-plugins-official
/plugin install frontend-design@claude-plugins-official
/plugin install code-review@claude-plugins-official
/plugin install code-simplifier@claude-plugins-official
```

Browse the marketplace for additional skills relevant to your project.

### agent-browser

```
npm install -g agent-browser # first
/plugin marketplace add vercel-labs/agent-browser
/plugin install agent-browser@agent-browser
```

### caveman (compressed I/O)

```
/plugin marketplace add JuliusBrussee/caveman
/plugin install caveman
```

### claude-mem (persistent memory)

```
/plugin marketplace add thedotmack/claude-mem
/plugin install claude-mem
```

---

```
  "enabledPlugins": {
    "skill-creator@claude-plugins-official": true,
    "superpowers@claude-plugins-official": true,
    "frontend-design@claude-plugins-official": true,
    "code-review@claude-plugins-official": true,
    "code-simplifier@claude-plugins-official": true,
    "caveman@caveman": true,
    "claude-mem@thedotmack": true,
    "context7@claude-plugins-official": true,
    "claude-md-management@claude-plugins-official": true,
    "playwright@claude-plugins-official": true,
    "figma@claude-plugins-official": true,
    "security-guidance@claude-plugins-official": true,
    "typescript-lsp@claude-plugins-official": true,
    "commit-commands@claude-plugins-official": true,
    "agent-browser@agent-browser": true
  },
```

## References

- [dropkit-starter-cc](https://github.com/vincentreynaud/dropkit-starter-cc) — droplet env bootstrap
- [Claude Code settings](https://docs.claude.com/en/docs/claude-code/settings)
- [Claude Code plugins](https://docs.claude.com/en/docs/claude-code/plugins)
