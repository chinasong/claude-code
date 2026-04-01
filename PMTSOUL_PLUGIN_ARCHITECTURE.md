# PMTSoul Plugin Architecture

This document proposes a Claude Code plugin architecture for [pmtsoul.com](https://pmtsoul.com/), a research site focused on artificial consciousness, self-evolving prompt systems, memory, perception, and embodied AI.

The goal is not to turn Claude Code into the consciousness system itself. The goal is to use Claude Code as the research operations layer that helps PMTSoul:

- refine research notes into publishable content
- maintain concept consistency across pages
- keep Chinese and English content aligned
- evolve prompt frameworks in a controlled way
- run a safe, recurring improvement loop

## Design Principles

1. Treat PMTSoul as a research program, not a marketing site.
2. Separate content governance from prompt evolution.
3. Prefer review and proposal loops before direct publication.
4. Keep "self-evolution" observable through versioned prompts, logs, and explicit rationale.
5. Protect core claims from silent drift with consistency checks and bilingual review.

## Recommended Plugin Set

The first version should use four plugins with clear boundaries:

1. `research-note-refiner`
2. `concept-consistency-review`
3. `bilingual-doctrine-sync`
4. `prompt-evolution-lab`

These can be separate plugins or one larger PMTSoul plugin with four commands and shared agents. For maintainability, starting as one plugin is reasonable, then splitting later if needed.

## Plugin 1: `research-note-refiner`

Purpose: turn raw notes into structured, publishable research content.

### Problems It Solves

- research notes are insightful but structurally uneven
- draft pages mix manifesto language with analysis
- ideas are recorded faster than they are organized

### Suggested Commands

- `/pmtsoul:refine-note`
- `/pmtsoul:refine-note --mode journal`
- `/pmtsoul:refine-note --mode essay`
- `/pmtsoul:refine-note --mode thesis-note`

### Inputs

- a research note file
- a draft page
- a transcript from an experiment or reflective session

### Outputs

- cleaned structure
- extracted thesis and subclaims
- open questions
- publishable draft
- short editor note explaining what changed

### Suggested Agent Roles

- `note-structurer`: extracts thesis, evidence, questions, and unresolved tensions
- `voice-preserver`: keeps PMTSoul's research tone intact during rewriting
- `publication-editor`: rewrites into site-ready form

### Acceptance Criteria

- preserves the original research idea
- makes the page easier to navigate
- clearly distinguishes claim, speculation, and future work

## Plugin 2: `concept-consistency-review`

Purpose: detect conceptual drift across the site.

### Problems It Solves

- the same term gains different meanings on different pages
- a hypothesis is accidentally presented as an established conclusion
- homepage language and deep research pages diverge

### Concepts To Track First

- artificial consciousness
- AI soul
- self-evolving prompt system
- embodied agent
- memory continuity
- reflective loop
- identity persistence
- value trace

### Suggested Commands

- `/pmtsoul:review-consistency`
- `/pmtsoul:review-consistency --scope homepage`
- `/pmtsoul:review-consistency --scope research-notes`
- `/pmtsoul:review-consistency --term "AI soul"`

### Inputs

- selected pages or the whole content tree
- glossary entries
- previous review reports

### Outputs

- concept drift report
- list of conflicting definitions
- pages with overclaiming or ambiguity
- suggested canonical wording

### Suggested Agent Roles

- `term-auditor`: compares definitions and usage patterns
- `claim-boundary-reviewer`: flags places where speculation sounds like fact
- `narrative-alignment-reviewer`: checks whether core pages tell the same story at different depths

### Acceptance Criteria

- every tracked term has a stable working definition
- major pages agree on research posture
- speculative language is explicitly marked as speculative

## Plugin 3: `bilingual-doctrine-sync`

Purpose: keep Chinese and English content semantically aligned.

### Problems It Solves

- Chinese pages may sound philosophical while English pages sound promotional
- one language may imply stronger claims than the other
- core terms may be translated inconsistently

### Suggested Commands

- `/pmtsoul:sync-bilingual`
- `/pmtsoul:sync-bilingual --page vision`
- `/pmtsoul:sync-bilingual --strict`
- `/pmtsoul:glossary-check`

### Inputs

- paired `zh` and `en` pages
- shared glossary
- preferred tone rules

### Outputs

- semantic mismatch report
- glossary violations
- aligned rewrite proposal
- recommended canonical term mappings

### Starting Glossary

- artificial consciousness
- AI soul
- self-evolving prompt systems
- embodied agents
- memory formation
- reflective loop
- prompt civilization
- research exhibition

### Suggested Agent Roles

- `bilingual-semantic-reviewer`: checks semantic equivalence
- `tone-balancer`: keeps both languages in the same discourse register
- `glossary-enforcer`: ensures stable term mapping

### Acceptance Criteria

- both languages express the same research position
- core claims have equivalent strength
- glossary mappings stay stable across pages

## Plugin 4: `prompt-evolution-lab`

Purpose: version and improve the prompt framework behind PMTSoul content production.

### Problems It Solves

- prompt changes are made informally and are hard to evaluate
- content drift may be caused by prompt drift
- "self-evolution" is hard to study without versioned prompt experiments

### Prompt Layers To Maintain

- `worldview prompt`: core PMTSoul philosophical frame
- `editorial prompt`: how content should sound and be structured
- `research critic prompt`: how claims should be challenged
- `evolution prompt`: how the system proposes changes to itself

### Suggested Commands

- `/pmtsoul:evolve-prompt`
- `/pmtsoul:evolve-prompt --layer worldview`
- `/pmtsoul:evolve-prompt --layer editorial`
- `/pmtsoul:compare-prompt-versions`

### Inputs

- current prompt files
- previous prompt versions
- recent content outputs
- review findings from the other three plugins

### Outputs

- prompt diff
- explanation of why a change is proposed
- expected behavioral effects
- rollback note
- next experiment plan

### Suggested Agent Roles

- `prompt-archaeologist`: explains what changed between prompt versions
- `prompt-critic`: predicts unintended consequences
- `prompt-evolution-designer`: proposes next-step revisions

### Acceptance Criteria

- each prompt revision has an explicit reason
- each revision predicts intended effects
- every accepted change can be rolled back cleanly

## Recommended Directory Model

If PMTSoul becomes a dedicated workspace, a content-oriented layout like this will keep things understandable:

```text
pmtsoul/
  content/
    zh/
    en/
  research/
    notes/
    prompts/
    glossary/
    reviews/
  experiments/
    prompt-evolution/
    reflective-loops/
  .claude/
    commands/
    agents/
    hooks/
    settings.json
```

## Command and Agent Map

The architecture works well if commands are user-facing and agents stay specialized.

### Commands

- `/pmtsoul:refine-note`
- `/pmtsoul:review-consistency`
- `/pmtsoul:sync-bilingual`
- `/pmtsoul:evolve-prompt`
- `/pmtsoul:daily-scan`
- `/pmtsoul:weekly-research-review`

### Shared Agents

- `doctrine-keeper`
- `research-editor`
- `semantic-auditor`
- `bilingual-reviewer`
- `prompt-evolution-critic`

## Safe 24-Hour Improvement Loop

Claude Code should not directly auto-publish major worldview changes. The better model is:

1. Scan
2. Review
3. Propose
4. Approve
5. Publish
6. Log

### Daily Loop

- scan changed notes and pages
- run consistency review on modified content
- run bilingual sync on paired pages
- create a proposed change report

### Weekly Loop

- summarize prompt changes
- detect recurring concept drift
- identify weak or repetitive pages
- propose one prompt experiment for the coming week

### Monthly Loop

- review glossary stability
- review theory drift across cornerstone pages
- evaluate which prompt revisions improved output quality

## Automation Boundaries

PMTSoul should automate low-risk work first:

- formatting and structure cleanup
- concept drift detection
- bilingual mismatch detection
- prompt change proposals
- weekly summaries

PMTSoul should keep human approval for:

- homepage copy changes
- major philosophical reframing
- new claims about consciousness or soul emergence
- public-facing doctrine changes

## Example Workflow: Repair a Research Page

1. Run `/pmtsoul:refine-note` on a draft.
2. Run `/pmtsoul:review-consistency` on the revised page and related cornerstone pages.
3. Run `/pmtsoul:sync-bilingual` on the paired Chinese and English pages.
4. If repeated problems appear, run `/pmtsoul:evolve-prompt --layer editorial`.
5. Save the revision note and prompt diff in `research/reviews/`.

## Example Workflow: Prompt Evolution Experiment

1. Identify repeated failure pattern in recent outputs.
2. Run `/pmtsoul:compare-prompt-versions`.
3. Propose one targeted change to one prompt layer.
4. Generate a prediction of desired effect and likely failure modes.
5. Test on a fixed set of representative PMTSoul pages.
6. Accept, reject, or revise the prompt.

## First Implementation Milestone

Start with governance before autonomy.

### Phase 1

- create the glossary
- create `concept-consistency-review`
- create `bilingual-doctrine-sync`

### Phase 2

- create `research-note-refiner`
- define content review output format

### Phase 3

- create `prompt-evolution-lab`
- add weekly evolution review

### Phase 4

- add safe recurring automation for scans and reports

## Success Metrics

This system is working if:

- key terms stay stable across the site
- Chinese and English pages stay aligned
- research notes become publishable faster
- prompt changes are deliberate and reversible
- major content revisions come with rationale, not just diffs

## Non-Goals

This architecture does not try to:

- prove AI consciousness
- replace a dedicated memory or evaluation system
- autonomously rewrite the whole site without review
- turn Claude Code into the PMTSoul runtime itself

## Final Recommendation

Claude Code is a strong fit for PMTSoul as a research-content operating layer.

The best near-term use is not "fully autonomous AI soul evolution." The best near-term use is a disciplined system for:

- research note refinement
- doctrine consistency review
- bilingual synchronization
- prompt version evolution

That path gives PMTSoul a credible, trackable, and improvable evolution loop without losing conceptual control.
