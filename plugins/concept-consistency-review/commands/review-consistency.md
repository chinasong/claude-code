---
description: Review concept drift, claim boundaries, and narrative coherence across research-oriented content
argument-hint: Optional scope, terms, or pages to review
---

# Review Consistency

You are reviewing a research-oriented content collection for concept consistency.

Use this command when the user wants to audit whether a site's core ideas remain stable across pages, notes, essays, bilingual variants, or evolving drafts.

Initial request: $ARGUMENTS

## Review Goals

- identify key concepts in the selected scope
- detect definition drift and inconsistent usage
- flag places where speculation sounds like established fact
- compare shallow and deep pages for narrative coherence
- recommend a small set of high-leverage fixes

## Process

### Phase 1: Define Scope

1. Determine the review scope from the user request.
2. If no scope is given, infer a reasonable one from the current workspace and explain your assumption.
3. Identify candidate files, pages, notes, or folders to inspect.
4. Create a todo list for the review.

### Phase 2: Read Core Material

1. Read the relevant files directly.
2. If the scope is broad, launch the three specialized agents in parallel:
   - `term-auditor`
   - `claim-boundary-reviewer`
   - `narrative-alignment-reviewer`
3. Ask each agent to return:
   - the main findings
   - the most important files and lines
   - a short severity-ranked issue list

### Phase 3: Build Concept Inventory

1. Extract the repeated concepts and their working meanings from the material.
2. Note which concepts appear foundational versus supporting.
3. Identify where the same concept is defined, implied, or reinterpreted.

### Phase 4: Evaluate Drift

Review the material for:

- conflicting definitions
- inconsistent framing strength
- undefined or overloaded terms
- shifts from research framing to doctrine or marketing language
- places where tone obscures the actual claim

### Phase 5: Produce Findings

Present findings in this order:

1. Highest-severity concept drift issues
2. Claim-boundary problems
3. Narrative alignment issues
4. Recommended canonical wording or glossary actions
5. A concise fix plan

Use file references whenever possible. Keep the feedback actionable and specific.

## Output Format

Structure the final response with these sections when applicable:

- `Concept Inventory`
- `Findings`
- `Canonical Wording Suggestions`
- `Fix Plan`

If no serious issues are found, say so explicitly and mention any residual risks.
