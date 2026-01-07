# ⚡ Quick Start: QC-Kit (Antigravity Edition)

Start using the World-Class Quality Control Squad in **2 minutes**.

## 1. Installation

The QC-Kit creates a "Squad" of agents inside your Antigravity environment.

### Step A: Locate your Brain
Find where your Antigravity Agent stores its workflows.
*   Standard (Mac/Linux): `~/.gemini/antigravity/workflows/`

### Step B: Deploy the Squad
Copy the 15 Agent Definitions into that folder.

```bash
# Clone the repository (if you haven't)
git clone https://github.com/olbboy/qc-kit.git

# Copy workflows
cp -r qc-kit/.agent/workflows/* ~/.gemini/antigravity/workflows/
```

## 2. Verification

Restart your Antigravity session.
Type `@` in the chat box. You should see the auto-complete list:
*   `@qc-master`
*   `@qc-testcase`
*   `@qc-automation`
*   ... (and 12 others)

## 3. Your First Interaction

### Scenario: "Generate Test Cases"
You have a User Story, you need test cases.
**Type:**
> `@qc-testcase Generate test cases for: "As a user, I can login with email and password."`

**Result:**
The **Test Designer Agent** will activate and generate:
*   ✅ Positive Cases (Valid Login)
*   ❌ Negative Cases (Invalid Password, Empty Fields)
*   🔀 Edge Cases (Max Length, SQL Injection)

### Scenario: "Write Automation Script"
You have test cases, you need Playwright code.
**Type:**
> `@qc-automation Convert these test cases to Playwright TypeScript.`

**Result:**
The **SDET Agent** will generate executable Playwright scripts with proper Page Object Model structure.

## 4. Power User Tips

*   **Flash Mode**: Switch agents instantly. `@qc-testcase` -> `@qc-automation` -> `@qc-report`.
*   **The Commander**: If lost, type `@qc-master help`. The Strategist will guide you.
*   **Tools**: Agents will automatically use `run_command(pytest)` and `run_command(playwright)`.

## 5. Troubleshooting

**Q: The agent isn't appearing?**
A: Ensure the `.md` files are in the root of your `workflows/` directory.

**Q: The generated test has syntax errors?**
A: Ask the agent: *"Run this test and fix any errors."*
