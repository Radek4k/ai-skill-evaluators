# Specification - Agent Skills

The complete format specification for Agent Skills.
Source: https://agentskills.io/specification

## Directory Structure

A skill must be contained in its own directory.

```
skill-name/
├── SKILL.md      # Required: metadata + instructions
├── scripts/      # Optional: executable code
├── references/   # Optional: documentation
├── assets/       # Optional: templates, resources
└── ...           # Any additional files or directories
```

## SKILL.md format

### Frontmatter

Skills must include YAML frontmatter at the top of the `SKILL.md` file, delimited by `---`.

```yaml
---
name: pdf-processing
description: Extract PDF text, fill forms, merge files. Use when handling PDFs.
license: Apache-2.0
metadata:
  author: example-org
  version: "1.0"
---
```

#### name field
- Must be 1-64 characters
- May only contain unicode lowercase alphanumeric characters (`a-z`) and hyphens (`-`)
- Must not start or end with a hyphen (`-`)
- Must not contain consecutive hyphens (`--`)
- Must match the parent directory name

**Valid examples:**
- `pdf-processing`
- `data-analysis`
- `code-review`

**Invalid examples:**
- `PDF-Processing` (uppercase not allowed)
- `-pdf` (cannot start with hyphen)
- `pdf--processing` (consecutive hyphens not allowed)

#### description field
- Must be 1-1024 characters
- Should describe both what the skill does and when to use it
- Should include specific keywords that help agents identify relevant tasks

**Example:**
```yaml
description: Extracts text and tables from PDF files, fills PDF forms, and merges multiple PDFs. Use when working with PDF documents or when the user mentions PDFs, forms, or document extraction.
```

#### license field
- Specifies the license applied to the skill
- We recommend keeping it short (either the name of a license or the name of a bundled license file)

**Example:**
```yaml
license: Proprietary. LICENSE.txt has complete terms
```

#### compatibility field
- Must be 1-500 characters if provided
- Should only be included if your skill has specific environment requirements
- Can indicate intended product, required system packages, network access needs, etc.

**Examples:**
- `compatibility: Designed for Claude Code (or similar products)`
- `compatibility: Requires git, docker, jq, and access to the internet`
- `compatibility: Requires Python 3.14+ and uv`

#### metadata field
- A map from string keys to string values
- Clients can use this to store additional properties not defined by the Agent Skills spec

**Example:**
```yaml
metadata:
  author: example-org
  version: "1.0"
```

#### allowed-tools field
- A space-separated string of tools that are pre-approved to run
- Experimental. Support for this field may vary between agent implementations

**Example:**
```yaml
allowed-tools: Bash(git:*) Bash(jq:*) Read
```

### Body content
The body contains the instructions for the agent. It should include:
- Step-by-step instructions
- Examples of inputs and outputs
- Common edge cases

## Optional directories

### scripts/
Executable code used by the skill.
- Be self-contained or clearly document dependencies
- Include helpful error messages
- Handle edge cases gracefully

### references/
Supporting documentation.
- `REFERENCE.md` - Detailed technical reference
- `FORMS.md` - Form templates or structured data formats
- Domain-specific files (`finance.md`, `legal.md`, etc.)

### assets/
Static assets and templates.
- Templates (document templates, configuration templates)
- Images (diagrams, examples)
- Data files (lookup tables, schemas)

## Progressive disclosure
1. **Metadata** (~100 tokens): The `name` and `description` fields are loaded at startup for all skills.
2. **Instructions** (< 5000 tokens recommended): The full `SKILL.md` body is loaded when the skill is activated.
3. **Resources** (as needed): Files (e.g. those in `scripts/`, `references/`, or `assets/`) are loaded only when required.

## File references
Reference internal files using relative paths in `SKILL.md`.

**Example:**
```markdown
See [the reference guide](references/REFERENCE.md) for details. Run the extraction script: scripts/extract.py
```

## Validation
Use the `skills-ref` tool to validate skills:

```bash
skills-ref validate ./my-skill
```
