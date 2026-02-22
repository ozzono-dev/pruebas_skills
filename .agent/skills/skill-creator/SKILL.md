---
name: skill-creator
description: Generates new skills for the agent. Use this skill when the user asks you to create a new skill to teach you how to perform specific tasks.
---

# Skill Creator

This skill provides the standard operating procedure for creating new skills for the agent.

## When to use this skill
- Use this when the user explicitly asks you to create a new skill.
- Use this when the user wants to teach you a new recurring workflow, convention, or set of instructions.

## How to create a skill

Follow these steps to create a new skill:

1.  **Understand the Skill's Purpose:** Gather requirements from the user. What should the new skill do? What are the specific instructions, conventions, or tools required?
2.  **Determine Name and Description:**
    -   *Name:* A unique identifier (lowercase, hyphens for spaces, e.g., `my-new-skill`).
    -   *Description:* A clear description of what the skill does, written in the third person, including keywords (e.g., "Generates unit tests for Python code using pytest conventions").
3.  **Create the Folder Structure:** Each skill must live in its own directory under `.agent/skills/`. For example: `.agent/skills/<skill-name>/`.
4.  **Create the `SKILL.md` file:** This is the only required file. Use the `write_to_file` tool to create it at `.agent/skills/<skill-name>/SKILL.md`. It **must** contain valid YAML frontmatter at the top with `name` and `description`.

    **Template for `SKILL.md`:**
    ```yaml
    ---
    name: <skill-name>
    description: <clear description from step 2>
    ---

    # <Human Readable Skill Name>

    Detailed instructions for the agent go here.

    ## When to use this skill
    - Use this when...
    - This is helpful for...

    ## How to use it
    - Step-by-step guidance, conventions, and patterns the agent should follow.
    - Mention any scripts or resources included in the skill folder.
    ```
5.  **Create Optional Folders:** Only if specifically needed for the skill, create:
    -   `scripts/` for helper scripts.
    -   `examples/` for reference implementations.
    -   `resources/` for templates and other assets.
6.  **Confirmation:** Inform the user that the skill has been successfully created and is ready to be used in future tasks or conversations.

## Best Practices for the SKILL.md Content
- **Keep it focused:** The generated skill should do one thing well.
- **Write clear descriptions:** The YAML description is what the agent uses to decide whether to activate the skill. Make it highly descriptive.
- **Include Decision Trees:** If the created skill handles complex tasks, include decision trees or step-by-step logic to help the agent choose the right approach when using the skill later.
