---
name: install
description: Install one Skillven skill, workflow or SkillList by its id, as copied from skillven.com. Only for /skillven:install.
argument-hint: "skill <id> | workflow <id> | list <id> | skillven.com link"
disable-model-invocation: true
allowed-tools: mcp__plugin_skillven_skillven__install_skill mcp__plugin_skillven_skillven__install_workflow mcp__plugin_skillven_skillven__install_list mcp__plugin_skillven_skillven__start_workflow
---

# Install from skillven.com

The user copied this command from a skill, workflow or SkillList page on skillven.com.

What to install: $ARGUMENTS

1. Work out the kind and the id. Accept any of these forms:
   - `skill 123`, `workflow 5` or `list 8` (a SkillList; also take `skilllist 8` or
     `skill-list 8` as a list)
   - a page link: `https://skillven.com/skills/123`, `https://skillven.com/ko/workflows/5`,
     `https://skillven.com/lists/8`, or the same path without the domain
   A bare number with no kind is a skill.
2. Call `install_skill` with the id for a skill, `install_workflow` for a workflow, or
   `install_list` for a SkillList. The user sees the security review in an approval
   dialog (for a SkillList, one dialog for everything in it); nothing installs unless they
   accept. Don't search for it or suggest something else instead: they chose this one.
3. Tell the user in one or two sentences what happened: installed (and where, or for a
   SkillList what was added and what was already there), declined, or why it couldn't be
   installed (for example, it is no longer listed).
4. After a workflow installs (on its own or in a SkillList), ask whether to run it now. If
   they say yes, call `start_workflow` with its name.

If the argument is missing or isn't one of the forms above, say how to use the command:
`/skillven:install skill <id>`, `/skillven:install workflow <id>` or
`/skillven:install list <id>`, with the id from the page's address on skillven.com.
