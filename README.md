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

## ⚙️ How to Use

1. **Clone the repository**:
   ```bash
   git clone https://github.com/Radek4k/ai-skill-evaluators.git
   ```
2. **Navigate to the evaluators**:
   Each evaluator is located in the `skills/` directory.
3. **Run Validation**:
   Follow the instructions in the specific `SKILL.md` file of the evaluator you wish to use.

## 🤝 Contributing

Contributions are welcome! If you have a new evaluator or an improvement to an existing one, please feel free to open a Pull Request.

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

---
Created by [Radek Kitner](https://kitner.cz)
