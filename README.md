# AI Skill Evaluators

A collection of tools and skills designed to validate, audit, and ensure the quality of AI agent skills, primarily focusing on compliance with the [agentskills.io](https://agentskills.io) specification.

## 🚀 Overview

This project provides a suite of evaluators that help developers and AI agents maintain high standards for portable, discoverable, and actionable agent skills. By ensuring skills follow standardized metadata and structural rules, we enable better agent performance and interoperability.

## 🛠️ Included Skills

### [Skill Quality Checker](skills/skill-quality-checker/SKILL.md)
Performs comprehensive validation of AI skills against the official specification.
- **Key Features**: Metadata validation, structure checking, relative path verification, and automated npx validation support.
- **When to use**: During skill development, before submission, or when auditing existing skill libraries.

## 📋 Standards Compliance

All skills in this repository aim for strict adherence to the **agentskills.io v1.2.0** specification, ensuring:
- **Discovery**: Optimized metadata for agent selection.
- **Portability**: Relative path usage for environment independence.
- **Activation**: Clear, actionable instructions for AI execution.

## 📦 Installation & Prerequisites

### Prerequisites
- **Node.js**: Required for running the validation tools and the `skills` CLI. You can download it from [nodejs.org](https://nodejs.org/).

### Installation Options

#### Option 1: Quick Add (Recommended)
Add individual skills directly to your project:
```bash
npx skills add https://github.com/Radek4k/ai-skill-evaluators/blob/main/skills/skill-quality-checker/SKILL.md
```

#### Option 2: Full Clone
Clone the entire repository to access all evaluators and tools:
```bash
git clone https://github.com/Radek4k/ai-skill-evaluators.git
```

## ⚙️ How to Use

Once installed or cloned, navigate to the specific skill directory (e.g., `skills/skill-quality-checker/`) and follow the instructions in its `SKILL.md` file. 

Generally, you can run validation using:
```bash
npx skills-ref validate <path_to_skill_to_check>
```

## 🤝 Contributing

Contributions are welcome! If you have a new evaluator or an improvement to an existing one, please feel free to open a Pull Request.

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

---
Created by [Radek Kitner](https://kitner.cz)
