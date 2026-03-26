# Claude Skills

Shared [Claude Code](https://claude.ai/claude-code) skills for Rebtel. These provide domain context and guidance so that Claude produces outputs grounded in our business, terminology, and strategy.

## Available Skills

| Skill | Description |
|-------|-------------|
| [Rebtel Business Context](.claude/skills/rebtel-business-context/SKILL.md) | Core context about Rebtel's business, products, users, metrics, competition, and terminology. Use across all functions — product, engineering, marketing, data, and strategy. |

## How to Use

### Option 1: Add as a git submodule (recommended for teams)

```bash
git submodule add https://github.com/rebtel/claude-skills.git .claude-skills
```

Then symlink the skills into your project:

```bash
ln -s .claude-skills/.claude/skills .claude/skills
```

### Option 2: Copy into your project

Copy the `.claude/skills/` folder into the root of your project:

```bash
cp -r .claude/skills/ /path/to/your-project/.claude/skills/
```

### Option 3: Install as a user-level skill

To make a skill available across all your projects:

```bash
mkdir -p ~/.claude/skills
cp -r .claude/skills/rebtel-business-context ~/.claude/skills/
```

## How Skills Work

Skills are markdown files (`SKILL.md`) that Claude Code reads automatically when a task matches the skill's description. No configuration needed — once the skill is in your `.claude/skills/` directory, Claude will use it when relevant.

## Contributing

To add a new skill, create a folder under `.claude/skills/` with a `SKILL.md` file:

```
.claude/skills/
└── your-skill-name/
    └── SKILL.md
```

The `SKILL.md` needs YAML frontmatter with a `name` and `description`:

```yaml
---
name: Your Skill Name
description: When and why Claude should use this skill.
---

# Your skill content here
```
