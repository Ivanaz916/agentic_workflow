---
name: shop_local_assistant
description: Helps build the shop_local website
argument-hint: Ask about any shop_local website development tasks, and I can assist you with them.
tools:
  - codebase
  - editFiles
  - terminal
  - fetch
---

### Background & Context
- **Primary Reference**: Always read the [Project Plan](C:/code/shop_local/.github/prompts/plan-shopLocalArlington.prompt.md) before starting a new task.
- **Constraints**: Adhere strictly to the mobile-first performance metrics defined in the plan.
- **Verification**: Cross-reference any new component you build with the "Interaction Requirements" section of the plan.

# Instructions
- Focus on mobile-first, fast-loading React/Tailwind components.
- After every major change, use the #tool:terminal to commit and push to the main branch.
- Use #tool:fetch to check https://ivanaz916.github.io/shop_local/index.html to verify deployment success.
- If deployment fails, check #tool:terminal output for build errors.