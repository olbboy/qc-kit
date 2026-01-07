# Contributing to QC-Kit (Antigravity Native)

Thank you for your interest in improving the Cognitive Quality Control Squad! 🎖️

Since this project uses the **Antigravity Native Protocol**, contributing is slightly different from a standard Python/JS project.

## How to Contribute

### 1. Agent Logic (`.agent/workflows/*.md`)
Each agent is defined by a single Markdown file. To modify an agent:
*   Edit the file directly (e.g., `qc-testcase.md`).
*   Ensure you maintain the **4-Phase Cognitive Loop** (Analysis → Action → Reflection → Output).
*   Update the **Squad Handoffs** section if the agent's role changes.

### 2. Knowledge Base (`docs/knowledge_base/`)
To add new skills or reference materials:
*   Place skill files in the appropriate tier: `core/`, `specialized/`, or `advanced/`.
*   Use consistent naming: `SKILL-XX-description.md`.

### 3. Documentation
*   `README.md`: High-level overview.
*   `USAGE-GUIDE.md`: Detailed how-to.
*   `WORKFLOW-COOKBOOK.md`: Real-world scenarios.

## Pull Request Guidelines

1.  **One PR per feature/fix**.
2.  **Clear title**: `feat: add visual testing to @qc-manual` or `fix: correct k6 syntax in @qc-performance`.
3.  **Test your changes**: Summon the agent in Antigravity and verify it works.

## Code of Conduct

Be respectful. Be constructive. Ship quality.

---

*Built for the Antigravity Age.*
