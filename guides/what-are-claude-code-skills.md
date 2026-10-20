# What are Claude Code skills? A complete guide

Claude Code skills are folders that contain a SKILL.md file: Markdown instructions, plus optional scripts and reference files, that teach Claude Code how to perform a specific task. When your request matches a skill's description, Claude loads that skill and follows its workflow.

## How do Claude Code skills work?

Each SKILL.md starts with YAML frontmatter containing a name and a description. Claude Code reads the descriptions of all installed skills, and when a request matches one, it loads the full instructions into context. Because only the short descriptions are always loaded, you can install many skills without slowing the agent down.

## Where do you install Claude Code skills?

- Personal skills: ~/.claude/skills/<skill-name>/SKILL.md, available in every project
- Project skills: .claude/skills/<skill-name>/SKILL.md inside a repository, shared with everyone who clones it
- Plugin skills: bundled inside Claude Code plugins

## What does a SKILL.md file look like?

```
---
name: launch-kit
description: Write a complete launch kit for a product. Use when the user is launching a product or asks for launch posts.
---

# Launch Kit

## Step 1: Gather facts
Read the README and landing page before asking questions...
```

## How do you write a good skill?

- Write the description as trigger conditions: what the skill does and exactly when to use it
- Give a step-by-step workflow, not general advice
- Include checklists the agent can verify item by item
- Define the output format so results are consistent
- List what the agent must never do, such as inventing data

## Skills vs. prompts vs. MCP servers

|  | Skill | Prompt | MCP server |
|---|---|---|---|
| What it is | Reusable instructions and scripts | One-off instructions | A tool/API the agent can call |
| Loaded | Automatically when relevant | Every time you type it | Always available as tools |
| Best for | Repeatable workflows and expertise | Quick one-time tasks | Connecting to external systems |

## Where can you get ready-made skills?

Skillwright publishes production-grade skills for shipping software: a free SEO + AEO + GEO audit, a free launch kit, and premium skills for landing pages, payments and pre-launch security reviews.
