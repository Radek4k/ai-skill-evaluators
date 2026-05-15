---
name: skill-quality-checker
description: Performs validation and quality control of AI skills according to the official agentskills.io specification. Use this skill when creating a new skill, modifying an existing one, or reviewing the .agents/skills/ directory structure.
metadata:
  version: "1.2.0"
  author: "Radek Kitner, kitner.cz"
---

# Skill Quality Checker

This skill ensures that all AI skills in the QArena project meet the standards defined at [agentskills.io](https://agentskills.io/specification). A properly defined skill enables efficient Discovery (finding the skill) and Activation (using the instructions) by the agent.

For the full technical details, see the [Complete Specification](references/SPECIFICATION.md).

## How to Use

Use this skill to systematically check the quality of another skill. Follow these steps:

1. **Identification**: Open the `SKILL.md` file of the skill you want to check.
2. **Technical Reference**: Consult the [Complete Specification](references/SPECIFICATION.md) for precise rules on naming, formatting, and structure.
3. **Metadata Review**: Verify that the frontmatter (especially `name` and `description`) matches the rules in the checklist below and the full specification. This is key for the "Discovery" phase.
4. **Instruction Check**: Review the document body. It must be clear, actionable, and free of placeholders.
5. **Structure Validation**: Verify that file paths to `scripts/` or `references/` are relative.
6. **Automated Validation**: If you have **Node.js** installed, run the following command (replace `<skill_path>` with the relative path to the skill directory, e.g., `.agents/skills/tools-guide`):
   ```bash
   npx skills-ref validate <skill_path>
   ```

## 📋 Quality Checklist

### 1. Metadata (Frontmatter)
- [ ] **Delimiters**: The block starts and ends with triple dashes `---`.
- [ ] **`name` field**:
    - [ ] Exactly matches the skill folder name.
    - [ ] Kebab-case format (lowercase, dashes).
    - [ ] Length 1-64 characters.
    - [ ] Does not contain consecutive dashes `--` or start/end with a dash.
- [ ] **`description` field**:
    - [ ] Length 1-1024 characters.
    - [ ] Clearly states **what** the skill does and **when** to use it.
    - [ ] Includes keywords for easy discovery (e.g., "Use when...", "When to use...").

### 2. Structure and Body
- [ ] **File**: Main instructions are in `SKILL.md`.
- [ ] **Relative Paths**: All links to files inside the skill (`scripts/`, `assets/`, `references/`) must use relative paths.
- [ ] **Folder Structure**:
    - `scripts/` for executable code.
    - `references/` for static documentation.
    - `assets/` for templates and resources.
- [ ] **Length**: Recommended body length for `SKILL.md` is up to 5000 tokens.

### 3. Technical Correctness
- [ ] **No Placeholders**: The skill must not contain sample code with "TODO" or "your code here".
- [ ] **Discovery Rule**: The metadata description must not be duplicated in the document body; the body should contain detailed "How-to" instructions.
