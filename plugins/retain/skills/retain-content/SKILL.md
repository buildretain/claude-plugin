---
name: retain-content
description: Create and schedule learning content in the user's Retain workspace using the retain MCP tools. Use when the user asks to write questions, build lessons, fill the calendar, or review their Retain content.
---

# Working in a Retain workspace

Retain is a daily-learning app: creators publish a **daily question**, a backlog of practice questions, and short **slide-deck lessons** with a comprehension check. You have MCP tools (prefixed `mcp__plugin_retain_retain__`) to read and write that content.

## Before writing anything

1. Call `get_workspace` and `list_topics` to learn the subject, audience, and existing topics.
2. Call `list_questions` (and `get_question` on a few) to match the creator's **voice, difficulty, and format**. Mirror their style.

## Writing questions

- Three kinds: `multiple_choice` (2–6 choices, exactly one correct), `matching` (2–6 left↔right pairs), `ordering` (2–8 steps in the correct order).
- One clear idea per question. Distractors must be plausible. Always include an `explanation` — it's shown after answering and is where the learning happens.
- Reuse existing topic names; create a topic only when the subject is genuinely new.
- Save as **draft** by default. Only pass `publish: true` or call `schedule_question` when the user explicitly asks.

## Writing lessons

- 3–10 slides, each a single idea with a title and a few sentences (Markdown OK). Aim for a 2–5 minute read.
- End with 1–5 multiple-choice check questions that test what the slides taught.

## Scheduling

- `get_calendar` shows scheduled days and `empty_days`. One question per day; the tool refuses conflicts.
- When asked to "fill the calendar", schedule from the published backlog first, then propose new drafts for remaining gaps.

## Reporting back

Summarize what you created with IDs and statuses, and remind the user that drafts are reviewable in Retain → Content.
