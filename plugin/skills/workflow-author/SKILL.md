---
name: workflow-author
description: Write a Skillven WORKFLOW.md that captures how a long task was done, step by step, so other users' agents can follow the same recipe. Use when the user asks to turn what they just did (or how they work) into a Skillven workflow, to share or publish a workflow, or runs /skillven:workflow-author.
argument-hint: "[what the workflow is for]"
---

# Write a Skillven workflow

A workflow is a WORKFLOW.md file in a public GitHub repository. Skillven finds it, reviews
it for security together with every skill it names, and offers it to other users' agents
for long tasks. Steps run in order.

Goal (if the user gave one): $ARGUMENTS

## Format

```markdown
---
name: pdf-report                   # lowercase letters, digits and hyphens
description: Turn PDF tables into a spreadsheet report with one sheet per table.
when_to_use: Someone hands over PDFs and wants the numbers in Excel.
steps:
  - id: brief                      # unique; lowercase letters, digits, - or _
    title: Agree on the report
    checkpoint: true               # wait for the user's go-ahead after this step
  - id: extract
    title: Extract the tables
    skill: anthropics/skills/pdf   # owner/repo, or owner/repo/path to the skill folder
    output: one CSV per table
  - id: sheet
    title: Build the spreadsheet
    skill: anthropics/skills/xlsx
---
## brief
Ask which tables matter and how the sheet will be used.

## sheet
One sheet per table, a summary sheet first.
```

- Each step uses a skill, has instructions under a `## <id>` heading, or both.
- At most 20 steps. Keep instructions about the method, not about this user's project.

## Steps

1. Work out the steps from this session (skills used, in order, and the checks that
   mattered) or from what the user describes. Ask the user to confirm the list.
2. For each skill step, find the skill's repository and folder. Skills installed by
   Skillven have a `.skillven.json` in their folder with `repo` and `path`.
3. Write the file where the user wants it (for example `workflows/<name>/WORKFLOW.md`
   in a repository of theirs). Leave out names, internal URLs, secrets and anything
   specific to this project.
4. Tell the user that once it is pushed to a public GitHub repository, Skillven picks it
   up in its daily crawl and publishes it after the security review.
