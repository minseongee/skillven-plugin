---
name: install
description: Install one Skillven skill or workflow by its id, as copied from skillven.com. Only for /skillven:install.
argument-hint: "skill <id> | workflow <id> | skillven.com link"
disable-model-invocation: true
allowed-tools: mcp__plugin_skillven_skillven__install_skill mcp__plugin_skillven_skillven__install_workflow mcp__plugin_skillven_skillven__start_workflow
---

# Install from skillven.com

The user copied this command from a skill or workflow page on skillven.com.

What to install: $ARGUMENTS

1. Work out the kind and the id. Accept any of these forms:
   - `skill 123` or `workflow 5`
   - a page link: `https://skillven.com/skills/123`, `https://skillven.com/ko/workflows/5`,
     or the same path without the domain
   A bare number with no kind is a skill.
2. Call `install_skill` with the id for a skill, or `install_workflow` for a workflow. The
   user sees its security review in an approval dialog; nothing installs unless they accept.
   Don't search for it or suggest something else instead: they chose this one.
3. Tell the user in one sentence what happened: installed (and where), declined, or why it
   couldn't be installed (for example, it is no longer listed).
4. After a workflow installs, ask whether to run it now. If they say yes, call
   `start_workflow` with its name.

If the argument is missing or isn't one of the forms above, say how to use the command:
`/skillven:install skill <id>` or `/skillven:install workflow <id>`, with the id from the
page's address on skillven.com.
