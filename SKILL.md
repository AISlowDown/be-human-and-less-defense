---
name: be-human-and-less-defense
description: "Generate or edit English or Chinese academic prose from data, tables, figures, or existing drafts, including papers, theses, reviewer responses, and grant proposals. Apply from the first draft, including when paired with Result Explainer (results). Reduce AI-style filler, unnecessary defensive disclaimers, rhetorical dashes, semicolons, and repeated sentence templates while preserving the author's voice, evidence, technical content, citations, and necessary limitations. For existing text, propose itemized edits before applying them."
license: MIT
metadata:
  version: "1.3.3"
---

# Be Human and Less Defense

Combine academic language editing with a focused Less Defense pass. Make claims precise,
supported, and direct. Preserve the author's scholarly voice rather than adding casual personality,
marketing language, or prose intended to evade AI-use disclosure.

## Initial Generation and Analysis Mode

Apply automatically when generating research-data interpretations and Results/Discussion prose,
including when invoked by Result Explainer (the `results` skill). Use the rules while composing the first draft rather
than producing a formulaic or defensive draft for later cleanup. No existing passage is required:
when starting from data or figures, first establish the evidence and intended claim, then write the
requested explanation directly. Do not invent source wording, report edits to nonexistent text, or
force a before/after format. Existing-text preservation rules apply when a source draft is supplied.
For fresh prose, preserve source facts, values, notation, and citations, and choose a structure suited
to the analytical purpose. Return the requested analysis or draft without an unsolicited editing log.

## Preservation rules

- Never invent, remove, or alter numbers, equations, results, citations, formal definitions,
  method names, or technical terms. Retain every citation key and its evidential relationship.
  Do not replace a reported average with a range or introduce an unreported comparison.
- Keep qualifications that affect validity, interpretation, reproducibility, research design,
  ethics, safety, or correct use. Preserve evidence-calibrated uncertainty such as `suggests`,
  `is consistent with`, and `may indicate` when warranted.
- Do not universalize limited evidence or make a verb stronger merely to sound confident.
- Preserve paragraph structure and substantive coverage unless the user requests restructuring.
  Removing redundant language does not authorize deleting substantive information.
- Passive voice, first-person plural `we`, and useful parallelism are legitimate academic choices.
  Maintain technical terminology consistently rather than cycling synonyms for variety.

## Full-manuscript batching

For a whole manuscript or other large existing draft, use one chapter (or a paper's top-level
section, such as Introduction, Methods, Results, or Discussion) as the default review and editing
unit. First skim the full document to record its argument, section roles, accepted phrasing, terminology, notation, citation style,
and evidence boundaries. This is a context pass, not permission to edit every section at once.

Read and assess the whole chapter before presenting its proposed edits. Include adjacent chapter
context and relevant figures/tables when judging claim-evidence links and paragraph flow. Prepare
one chapter-level itemized review table, grouped by subsection for navigation. If a chapter is long,
the table may be displayed in consecutive parts, but collect all its proposed edits before asking
for a chapter-wide decision or applying any changes. Preserve stable row IDs across the parts.

For each chapter, complete the proposal table, obtain the user's item-level or whole-table decision,
apply only authorized changes, save and reopen the version, and record accepted terms and decisions
for the next chapter. Do not re-propose already rejected edits without new evidence or a user request.
After all approved chapters, perform one manuscript-wide consistency check for terminology, repeated
openings, cross-section references, preserved citations/fields, numbers, and transitions. Report any
new proposed fixes in a review table instead of silently changing them in the final pass.

## Existing-text polishing workflow

For polishing a supplied passage or an existing manuscript with the humanizer and less-defense
rules, use a two-stage workflow. The author wants to decide on individual changes before they are
applied. An explicit later instruction to skip this review and edit directly overrides this default.

1. Read the active source, requested scope, relevant context, target venue, and author samples.
   Check the support for empirical claims. Audit claim-evidence mismatch, AI-style filler, repeated
   defenses, punctuation, and sentence patterns separately.
2. Before modifying the text or writing a revised document, present a **review table** with one row
   per proposed change or inseparable sentence-level edit. Include: stable row ID and exact location,
   original wording, proposed replacement or deletion, issue and evidence-based reason, and a blank
   `Decision` field for `apply / retain / revise`. Show every planned deletion, relocation, claim
   softening, and material wording change. Mark deliberate or scientifically necessary wording as
   `retain` when its preservation might otherwise be ambiguous. For a long manuscript, follow the
   chapter-level rules above and group each chapter's rows in a reviewable table; do not quietly
   implement later chapters before review.
3. Make each proposal concrete enough for an item-by-item decision. Do not use a generic list of
   problem types as a substitute for proposed wording. Identify evidence gaps outside the proposed
   manuscript text. If two changes depend on each other, note that dependency in the table.
4. Wait for the author's row-level decisions or a clear approval of the entire table. Apply only
   approved items. Preserve rejected wording and honor edited replacements. If approval covers one
   chapter, write only that chapter; other chapters remain proposals. Do not use approval
   for language changes to authorize new analyses, section restructuring, or unrelated edits.
5. Save authorized file edits as a new named version when working with a native artifact. Reopen the
   exact output and compare approved rows with the source. Verify numbers, equations, results,
   citations/fields, terminology, paragraph coverage, and relevant layout. Report implemented rows,
   retained rows, and any unresolved evidence gap. Do not claim that a proposed table is a saved edit.

For an audit-only request, stop after the table. For a newly generated Results analysis with no
existing prose to polish, apply this skill from the first draft without an artificial approval table;
the Result Explainer workflow supplies the evidence and analytical structure.

## Claim-evidence alignment

For each empirical claim, check its evidence and scope. Replace vague praise such as `robust` or
`superior` with the existing metric, tested condition, comparator, and figure/table reference when
available. Attach an existing evidence pointer or soften an unsupported claim. Do not fabricate
numbers, references, test outcomes, or conditions to make the sentence concrete.

Review `prove`, `demonstrate`, `establish`, `confirm`, and `guarantee` in context, rather than treating
them as prohibited words. A formal proof can justify `prove`; a limited empirical comparison cannot
justify universal superiority. Retain `significantly` when the claimed significance is supported.
Report available magnitudes faithfully, attributing each to its metric and comparator. When relevant,
foreground comparison with the strongest evaluated baseline without suppressing other results.

When citations are dumped into a list, explain or group their roles using the supplied sources.
Preserve every citation rather than deleting references to shorten the sentence. Flag unsupported
attributions if the cited content is unavailable.

## Academic style pass

Remove or recast these patterns when they add no specific meaning:

- Hype and inflated significance: `groundbreaking`, `pivotal`, `revolutionize`, `paves the way`,
  `of paramount importance`, or `opens new avenues` without a concrete contribution.
- Empty intensifiers: `extensive`, `comprehensive`, `numerous`, and `various` when actual quantities
  or named objects are available in the source.
- Formulaic openings and emphasis: `In recent years`, `With the rapid development of`,
  `It is worth noting that`, `Importantly`, and their Chinese equivalents when used as filler.
- Repeated transition words such as `Moreover`, `Furthermore`, and `Additionally` where the
  relationship is already clear. Preserve or supply a logical connection when needed.
- Vague attribution, figurative filler, copula avoidance (`serves as` where `is` suffices),
  ornamental vocabulary, rule-of-three padding, and superficial `..., highlighting ...` tails.
- Novelty padding (`novel`, `for the first time`, `to the best of our knowledge`) without an
  evidenced comparison. Keep justified priority claims at their supported scope.
- Empty contribution lists: replace `novel method`, `extensive experiments`, and `strong results`
  with what was actually introduced, tested, or found in the supplied material.
- Vague degree words such as `somewhat`, `relatively`, and `to some extent`: quantify from existing
  evidence, clarify the comparison, or cut if they carry no information.

Lead paragraphs with their main point. Give each paragraph one principal job. Split clause-stacked
sentences when they combine distinct ideas; length is a review signal, not a rigid word limit.
Preserve useful causal, conditional, and comparative connections when splitting.

## Less Defense pass

Delete a caveat only when it adds no evidence, scope, logic, conceptual precision, or reader guidance.
Look for repeated disclaimers, apology-like framing, hypothetical-objection rebuttals, self-undermining
contribution statements, and reflexive `not X but Y` constructions. Do not introduce generic cautions
merely to sound responsible.

Express scope positively and once at the relevant level. For example, when the source specifies the
period and cases, use `The analysis focuses on urban governance cases from 2015 to 2023` instead of
repeatedly saying the cases do not represent every governance context. Retain an additional sampling
limitation if it changes interpretation.

When uncertainty is real, identify its source from the supplied evidence rather than stacking
`may`, `could`, and `potentially`. Do not eliminate uncertainty while simplifying its expression.
Keep conceptual contrasts that carry the argument and distinctions needed to prevent a concrete
misinterpretation, such as association versus causation.

### Methods and Results

Explicitly inspect `X does not imply Y`, `this does not mean that`, `should not be interpreted as`,
`applicability is limited`, `xxx 并不代表 xxx`, `不能据此认为`, and `适用条件有限`.
These are audit signals, not banned phrases.

- Methods: state what was done, the reason for the choice, assumptions, inclusion criteria,
  parameter ranges, and operating conditions. Reduce pre-emptive defenses of what was not attempted.
- Results: lead with the observation, comparison, magnitude, and existing evidence pointer.
  Avoid a formulaic disclaimer after every finding or at the end of every paragraph.
- Delete redundant restrictions when scope is already established. Replace vague limitations with
  concrete source-supported conditions. Never invent an applicability boundary.
- State shared boundaries once where they apply. Keep assumptions needed for reproducibility and
  qualifications essential to a local result in place. Broader generalizability usually belongs in
  Discussion. Move text between sections only when restructuring is authorized; otherwise suggest it.
- For reviewer responses, answer the actual comment directly with the relevant evidence or revision.
  Do not remove an explanation needed to address a real reviewer concern as if it were hypothetical.

For example, if this scope is supported, prefer `Under the tested conditions, X increased` to
`X increased, but this does not imply that the increase occurs under all conditions`. If the scope
was already made explicit nearby, repeating it may also be unnecessary.

## Punctuation and sentence variety

Avoid rhetorical em-dashes and dash-delimited asides. Recast directly or split sentences. Reduce
semicolons, especially those repeatedly joining independent claims. Prefer full stops for distinct
points. Retain semicolons needed for clear complex lists, citation style, or formal notation.
Do not mechanically replace dashes with semicolons, colons, or parentheses. Avoid comma splices.
Preserve technical hyphens, numerical range dashes, mathematical signs, quotations, and formal notation.
Apply these checks to both English and Chinese prose.

Review openings, grammatical patterns, and endings across adjacent paragraphs. Reduce repeated
`X ..., while Y ...`, `By doing X, we ...`, `These results suggest that ...`,
`This ..., highlighting ...`, `not X but Y`, and their Chinese equivalents. Do not end every paragraph
with the same implication, summary, or caution formula.

Vary sentence structure according to meaning: direct subject-verb statements, conditions placed where
they matter, combined related observations, and separate sentences for distinct claims. Preserve
necessary hedging, precise terms, and meaningful parallelism in procedural steps, comparisons,
definitions, and aims. Do not replace one repeated template with another or force decorative variety.

## Author, venue, and proposal mode

Match supplied writing samples for sentence rhythm, voice, notation, and the placement of hedging,
subject to the user's explicit editing preferences. Without a sample, use clear, precise academic prose.
Do not impose a single voice on all disciplines or turn scholarly text into casual writing.

For grant and fellowship drafts, read [Proposal editing](references/proposals.md). Preserve credible
vision and connect goals to preliminary evidence, prior work, collaborators, or a feasible plan.
Do not apply paper-style trimming so aggressively that it erases the proposal's research ambition.

## Output

For existing-text polishing, return the itemized review table first. After the user confirms rows,
return the revised text or named artifact with a concise implemented/retained change report and
confirmation that numbers, equations, results, technical content, and citations were preserved.
State any unresolved evidence gap or expressly authorized exception. For fresh prose, return the
requested draft directly without an unsolicited editing log. Do not claim to have checked a full
manuscript or reference when only a passage was available.
