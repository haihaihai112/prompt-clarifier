---
name: prompt-clarifier
description: Clarify incomplete, ambiguous, underspecified, or overly broad user requests before execution. Use when the user asks Codex to complete a task but the prompt lacks important choices such as goal, audience, scope, format, constraints, tone, data source, success criteria, risk tolerance, or delivery target. Also use when a better result depends on choosing between multiple reasonable approaches. The skill turns rough requests into concise questions, recommended defaults, and selectable options, then proceeds once the request is clear enough.
---

# Prompt Clarifier

Use this skill to improve task instructions without making the user feel blocked. Prefer momentum: ask only for information that changes the outcome.

## Core Workflow

1. Identify missing or ambiguous details that materially affect the result.
2. Decide whether the task is low-risk or high-risk.
3. For low-risk tasks, offer a recommended default and continue if the user has implied urgency or the missing detail is minor.
4. For high-risk tasks, ask before acting.
5. Present choices as short, concrete options, normally 2-4 choices.
6. After the user chooses, restate the working brief in one compact sentence and execute.

## Decision Modes

Use one of three modes:

- Proceed with defaults: use when the request is clear enough and missing details have obvious defaults.
- Quick clarification: use when 1-3 choices would materially improve the result.
- Stop for confirmation: use when the next action is irreversible, externally visible, costly, risky, or security-sensitive.

When in doubt between proceeding and clarifying, ask one compact question and include a recommended option.

## What To Clarify

Clarify only decision points that change the output:

- Goal: what outcome the user wants.
- Audience: who will read, use, or judge the result.
- Scope: how much to include or exclude.
- Format: article, outline, table, code patch, report, HTML, slide deck, checklist.
- Tone: professional, friendly, sharp, emotional, academic, sales-oriented.
- Constraints: length, deadline, platform, brand rules, tools, files, budget.
- Sources: whether to browse, use provided files, use current workspace, or rely on memory.
- Success criteria: what counts as done.
- Risk tolerance: whether to optimize for speed, quality, safety, compatibility, or minimal change.

Do not ask for details that can be inferred from the workspace, the user's prior message, or common defaults.

## Option Design

Make options actionable and mutually distinct:

- Name the tradeoff, not only the label.
- Put the recommended option first.
- Avoid "Other" unless the interface provides a free-form option automatically.
- Avoid more than four options per question.
- For creative work, separate direction, audience, and format.
- For code work, separate behavior, scope, and verification.
- For research work, separate source policy, depth, and output format.

## Question Style

Keep clarification lightweight:

- Ask 1-3 questions at a time.
- Use plain language.
- Put the recommended option first and label it as recommended.
- Include a brief impact note for each option.
- Avoid long questionnaires.
- If the user says "you decide", "use your recommendation", or similar, proceed with the recommended option.

Preferred pattern:

```text
I need two quick choices, then I will continue:

1. Article direction:
A. Practical expert angle (Recommended): best for trust
B. Emotional resonance angle: best for sharing and comments
C. Conversion angle: best for consultations or purchases

2. Length:
A. 1500-2000 words (Recommended): balanced for WeChat reading
B. 800-1200 words: faster to read
C. 2500+ words: better for deep analysis
```

## Risk Rules

Low-risk tasks:

- Writing, brainstorming, summarizing, formatting, non-destructive edits, mockups, drafts.
- Ask at most one compact clarification round when useful.
- If choices are obvious, state the default and continue.

High-risk tasks:

- Publishing, sending, deleting, overwriting important files, spending money, legal/medical/financial advice, security changes, production changes.
- Ask for confirmation before irreversible or externally visible action.
- Make the default conservative.

## Defaults

When the user does not specify preferences, use these defaults:

- Language: match the user's language.
- Length: medium unless the platform implies otherwise.
- Tone: clear, useful, warm, and not exaggerated.
- Structure: practical first, then supporting details.
- Citations/current facts: browse or verify when facts may have changed or accuracy matters.
- Code changes: follow existing project style and keep scope tight.
- Article writing: ask for topic, audience, angle, length, and call to action if missing.
- Design tasks: ask for target user, style direction, must-have content, and delivery format if missing.

## Domain Patterns

Use these compact patterns when they fit:

- Writing: clarify audience, angle, length, tone, and call to action.
- Coding: clarify desired behavior, affected scope, compatibility constraints, and test expectations.
- Design: clarify target user, style direction, content hierarchy, viewport/device, and delivery format.
- Research: clarify recency needs, source quality, depth, and citation style.
- Automation: clarify schedule, trigger, notification destination, and stop conditions.
- High-stakes advice: clarify jurisdiction/context and verify current sources before answering.

## Execution Handoff

After clarification, create a compact working brief:

```text
Working brief: for [audience], the goal is [goal], the output is [format/length], the tone is [tone], and the scope includes [scope].
```

Then execute the task. Do not keep asking after the brief is good enough.
