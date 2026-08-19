---
name: skill-glm-delegation-with-brief
metadata:
  version: "1.2.0"
description: >-
  Delegate mechanical work to GLM with a 4-part brief. Use when the user says
  GLM으로 시켜, GLM 위임, glm brief, 지시서 써줘, 코딩 위임, 반복 작업 GLM,
  or delegation brief. Do not use for architecture, scoring, or user-facing talk.
---

# GLM Delegation with Brief

Executor designs. GLM executes from a brief **after** the plan passed `orchestrator-consultant-gate` (work order → GATE → then mechanical change). Score the brief with `skill-multi-model-overconfidence-guard` prompt axes before send (especially concrete + no judgment).

## Brief

```markdown
## 작업: [verb + object]
### 1. Files (path + role)
### 2. Spec (input → output → behavior)
### 3. Constraints (framework, style, forbidden)
### 4. Out of scope
```

Pass: every path listed; zero “적절히”/“필요하면”; framework named; ≥1 out-of-scope; GLM can run without deciding.

Yes: scaffold, file edits, README, tests, migration, CSS.  
No: architecture, scores, security, talking to the user, inventing the plan.

```bash
glm -p "$(cat brief.md)" --allowedTools Edit,Write,Read --add-dir <dir>
```

Templates: `templates/01-app-scaffold.md` … `07-test-write.md`. Verify output before treating the work order as done. Do not call without the 4-part brief.
