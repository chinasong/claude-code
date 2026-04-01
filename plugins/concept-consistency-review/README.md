# Concept Consistency Review Plugin

Review conceptual drift across research-driven content collections, especially sites that mix manifesto language, experimental notes, philosophy, and bilingual publishing.

This plugin is a strong fit for PMTSoul-style projects where the core challenge is not only writing new pages, but keeping core ideas stable as the site evolves.

## What It Does

The `/review-consistency` command helps you audit whether a research site uses its central concepts in a stable, legible, and defensible way.

It is designed to catch issues such as:

- the same term meaning different things on different pages
- speculative claims being written as settled conclusions
- homepage language drifting away from deeper research pages
- pages using inconsistent tone or research posture

## Command

### `/review-consistency`

Runs a structured concept review on the current content set or a user-specified scope.

**Example usage:**

```bash
/review-consistency
```

```bash
/review-consistency Review PMTSoul homepage, vision page, and research notes for concept drift around AI soul, memory continuity, and reflective loop.
```

## Review Outputs

The command is designed to produce:

- a concept inventory
- a concept drift summary
- claim-boundary issues
- narrative alignment issues
- recommended canonical wording
- a short prioritized fix plan

## Agents Included

- `term-auditor`: checks whether key terms are being used consistently
- `claim-boundary-reviewer`: finds places where speculation may sound like fact
- `narrative-alignment-reviewer`: compares shallow and deep pages for coherence

## Best Fit

Use this plugin when a project:

- publishes research notes and essays side by side
- evolves its theory over time
- uses repeated concepts that need stable definitions
- mixes Chinese and English content
- wants to improve quality without flattening the author's voice

## Suggested Workflow

1. Run `/review-consistency` on a selected scope.
2. Review the highest-severity concept drift issues.
3. Update glossary or canonical wording if needed.
4. Revise content.
5. Re-run the review after the edits.

## PMTSoul-Oriented Concepts To Track

Good starter concepts for PMTSoul-style research:

- artificial consciousness
- AI soul
- self-evolving prompt system
- embodied agent
- memory continuity
- reflective loop
- identity persistence
- value trace

## Notes

This plugin is intentionally review-oriented. It is meant to improve conceptual integrity before you build heavier automation around prompt evolution or scheduled content repair.
