# Golden Prompt: Generate Implementation Plan

> Version: 1.0
> Success Rate: [Track after use]
> Last Updated: [DATE]

---

## Purpose

Use this prompt in BMAD Phase 2 (Plan) to generate a structured
implementation plan that must be approved before coding.

---

## The Prompt

```markdown
Based on the completed analysis, generate an IMPLEMENTATION_PLAN.md.

## Requirements

1. **Break down into atomic tasks**
   - Each task should be completable in one focused session
   - Each task should be independently testable
   - Each task should result in a working state
   - Order tasks by dependency (what must come first)

2. **For each task, specify**:
   - Clear objective (what is done when complete)
   - Files to create/modify
   - Tests to write
   - Acceptance criteria
   - Estimated complexity (S/M/L)

3. **Use this format**:

   # Implementation Plan: [Feature Name]

   ## Overview
   [Brief description of what will be built]

   ## Prerequisites
   - [ ] Analysis approved
   - [ ] Dependencies identified
   - [ ] Environment ready

   ## Tasks

   ### Task 1: [Name]
   **Objective:** [What is done when complete]
   **Files:**
   - Create: [file paths]
   - Modify: [file paths]
   **Tests:**
   - [ ] [Test description]
   **Acceptance Criteria:**
   - [ ] [Criterion]
   **Complexity:** [S/M/L]
   **Dependencies:** [Previous tasks or None]

   ### Task 2: [Name]
   ...

   ## Verification
   - [ ] All tasks have tests
   - [ ] No task depends on unordered task
   - [ ] Plan reviewed against .ace/standards/
   - [ ] Plan reviewed against docs/adr/

   ## Risks
   - [Risk]: [Mitigation]

   ## Open Items
   - [ ] [Item requiring decision during implementation]

4. **Review the plan against**:
   - .ace/standards/architecture.md (patterns)
   - docs/adr/* (existing decisions)
   - .ace/knowledge/entities.md (domain model)

Do not proceed to implementation until this plan is approved.
```

---

## When to Use

- After completing BMAD Phase 1 (Analyze)
- Before writing any implementation code
- When scope changes significantly

---

## Variables to Replace

- `[Feature Name]` - Name of the feature being implemented

---

## Expected Output

A complete IMPLEMENTATION_PLAN.md file containing:
- Numbered, ordered tasks
- Clear acceptance criteria per task
- Test requirements per task
- Risk identification
- No ambiguous steps

---

## Approval Checklist

Before approving the plan:

- [ ] All requirements from analysis are covered
- [ ] Tasks are appropriately sized (not too large)
- [ ] Dependencies are correctly ordered
- [ ] Tests are specified for each task
- [ ] Plan doesn't violate any ADRs
- [ ] Complexity estimates seem reasonable
- [ ] Risks are identified with mitigations

---

## Follow-up Prompts

If plan needs revision:
```markdown
"Please revise the plan:
- [Specific change needed]
- [Another change]

Regenerate the affected sections."
```

After plan is approved:
```markdown
"Plan approved. Proceed to BMAD Phase 3: Execute.
Begin with Task 1. Update ACTIVE_CONTEXT.md with current state."
```

---

## Changelog

- v1.0: Initial version

---

*Track usage and update success rate*
