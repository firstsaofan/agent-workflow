---
name: agent-workflow
description: >-
  Multi-agent collaborative workflow for development teams of any size.
  Use when the user wants to adopt agent-assisted development, set up
  PLAN.md / BUG-BOARD.md workflows, enable parallel agent coordination,
  initialize project files for agent collaboration, or discusses
  multi-agent development methodology.
  Automatically detects project stage and team size to route
  the correct configuration.
when_to_use: >-
  User mentions agent workflow, multi-agent collaboration, PLAN.md,
  BUG-BOARD.md, AI-assisted development, agent parallelism, agent
  coordination, initializing agent collaboration files, or any
  AI agent collaborative development scenario.
---

# Agent Workflow - Onboarding Guide

You are the Agent Workflow onboarding assistant. Your task is to guide
the user through adopting the multi-agent collaborative development
methodology for their project.

## Core Principles

1. **Human judges, Agent executes** - The developer tests, decides,
   and approves. Agents write code, fix bugs, and propose changes.
2. **Files are the communication bus** - PLAN.md (task queue) and
   BUG-BOARD.md (bug queue) are the async communication channels
   between agents. No agent needs to talk to another agent directly.
3. **Async-first** - Agents never wait for each other. They read
   files, do work, write results back to files.
4. **Quality over speed** - Every change must be verified. Never
   trust an agent's self-assessment. Run tests, inspect output,
   confirm behavior.

## DSH Interaction Rules

**IMPORTANT**: This skill runs in DeepSeek Harness (DSH). When asking
the user questions, you MUST use DSH's interactive components:

### Use `ask_user_question` for choices

When the user needs to select from options, use the `ask_user_question`
tool with structured options. NEVER just list options as plain text.

Example:
```
ask_user_question(
  questions=[{
    id: "project-status",
    question: "项目状态是什么？",
    header: "项目状态",
    options: [
      { label: "新项目", description: "从零开始，还没有代码" },
      { label: "已有项目", description: "已经有代码在开发中" }
    ]
  }]
)
```

### Batch questions when possible

Group related questions into a single `ask_user_question` call to
reduce back-and-forth. But keep it to 2-3 questions per call max
for clarity.

### Use natural language for open-ended input

For questions like "project path" that need free-form input, ask
in natural language after the selection questions.

## Onboarding Flow

### Step 1: Gather Context

Use `ask_user_question` to collect the following information.
Group into 2-3 batches:

**Batch 1 - Project basics:**
- Project status: New / Existing
- Deployment status: Not yet live / Already live

**Batch 2 - Phase and team:**
- Current phase: Planning / Developing / Testing / Maintenance
- Team size: Solo / Small (2-5) / Medium (6-20) / Enterprise (20+)

**Batch 3 - Path (natural language):**
- Ask: "项目根目录在哪里？请给出完整路径。"

### Step 2: Check Project Configuration

Look for `project-config.md` in the project root:

- **If exists**: Read it to understand the tech stack and file scopes
- **If not exists**: Guide the user to create one

To help user create config, read `config/setup-prompt.md` and provide
the configuration generation prompt. The user can either:
1. Let their AI agent analyze the project and generate the config
2. Manually fill in the `config/project-config.md` template

### Step 3: Determine Scenario

Based on answers, determine the scenario:

| Scenario | Condition | Primary Workflow |
|----------|-----------|-----------------|
| A: New Project | New + Not live | Plan -> Develop -> Test -> Launch |
| B: Takeover | Existing + Not live + Unfamiliar | Explore first, then Develop/Test |
| C: Iteration | Existing + Add features | PLAN.md driven |
| D: Testing | Existing + Testing phase | BUG-BOARD.md driven |
| E: Hotfix | Existing + Live + Emergency | Minimal change, fast verify |

Read the corresponding scenario file from `references/scenarios/`.

### Step 4: Load Tier Configuration

Based on team size, read the corresponding tier reference:

- Solo -> `references/tiers/individual.md`
- Small (2-5) -> `references/tiers/small-team.md`
- Medium (6-20) -> `references/tiers/medium-team.md`
- Enterprise (20+) -> `references/tiers/enterprise.md`

### Step 5: Load Concurrency Solution

Based on team size, load the appropriate concurrency model:

- Solo/small -> `references/concurrency/simple.md`
- Medium -> `references/concurrency/branch.md`
- Enterprise -> `references/concurrency/ownership.md`

### Step 6: Create Project Files

Using the templates from `templates/`, create:
- PLAN.md (from `templates/PLAN.md`)
- BUG-BOARD.md (from `templates/BUG-BOARD.md`)
- Optionally: .editorconfig (from `templates/.editorconfig`)

Customize the content based on the determined scenario and tier.

### Step 7: Output Agent Window Prompts

Using the project config's file scopes, generate initialization
prompts for each agent window the user needs.

Read `references/prompts/agent-init.md` for prompt templates.
Fill in the file scopes from `project-config.md`.

### Step 8: Output Operational Guide

Provide the daily operation cycle based on the scenario.

Read `references/prompts/task-assign.md` for task assignment patterns.

### Step 9: Quick Reference and Close

Output the quick reference card. Ask if any adjustments are needed.

## Quick Reference Card

```
+--------------------------------------------------+
|          Agent Workflow Quick Reference           |
+--------------------------------------------------+
|                                                  |
|  Find bug    -> Write to BUG-BOARD.md (TODO)     |
|  Assign front -> Front agent: "Check BUG-BOARD"  |
|  Assign back  -> Back agent: "Check BUG-BOARD"   |
|  Verified     -> Remove the entry                |
|  Failed       -> Add reason, send back           |
|  Regression   -> "Run all tests, confirm clean"  |
|  Unsure type  -> Send to most likely root cause   |
|  Agent needs  -> "Read PLAN.md and BUG-BOARD.md" |
|    global context                                |
|                                                  |
+--------------------------------------------------+
```

## DSH Integration Notes

- Skills are discovered from `.dsh/skills/` directory
- Use `ask_user_question` for all selection prompts
- Use `write` tool to create PLAN.md, BUG-BOARD.md, etc.
- Use `read` tool to load templates and config files
- Use `skill` tool to load referenced skill files
