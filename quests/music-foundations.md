# Music foundations: an adaptive discovery quest line

**Status: published reference and plan; not executable quests.** This package documents an existing musical learning path and a proposed Brain discovery layer. It does not add music datasets, audio, app features or a proven training recipe.

## Existing practice path

The reference is the [Kodály Center Grade 1 curriculum](https://www.kodalycollection.org/curriculum_grade1.cfm), specifically the [Holy Names curriculum PDF](https://www.kodalycollection.org/pdf/grade1_curriculum.pdf) credited to Laskey (2014). It spans 70 lessons, assumes kindergarten musical experience, and addresses Kodály-trained teachers. It is not a zero-experience self-teaching course or an official Brain partnership.

The exact lesson anchors, short summaries and PDF page references are in [the manifest](music-foundations.json), under `source_milestones`. Begin with pulse and rhythm foundations before named pitch work. The anchor ranges organize this adaptation; they do not replace all activities in the source.

Consult the original curriculum for instruction and repertoire. This repository copies no songs, notation, audio or lesson plans and asserts no redistribution rights. No original Brain exercises are supplied in this release. Any future original exercises must be labeled as ours and kept separate from official source material.

## Proposed Brain quests

These questions and experiments are **our adaptation**, not instructions attributed to the curriculum's authors. Their purpose is to discover what the model does. We do not know how to optimize its training.

| Quest | Question | What progress enables |
| --- | --- | --- |
| Find the pulse | Can the representation distinguish a regular pulse from freely timed input? | A checked timeline for timing experiments |
| Keep the pulse while speed changes | What changes if timing changes but event order stays fixed? | A declared timing contract |
| Separate pulse from pattern | Can onsets and durations be related to beats without losing information? | Interpretable rhythm experiments |
| Follow pitch direction | Can up/down pitch movement retain its rhythm? | A verified pitch-and-duration mapping |
| Explore so-mi | What happens on a bounded two-pitch musical example? | A baseline for replay or missing-evidence questions |
| Explore la | Does a finding persist when the material expands? | Evidence about the finding's scope |
| Make silence explicit | Is a rest different from absent input? | A checked representation of silence |
| Explore do | What survives a broader vocabulary? | A better-defined next comparison |
| Explore re | Does a local finding transfer? | A scoped finding or a new unresolved question |

The order supplies musical scaffolding. The experiment graph branches from observations and can revisit earlier material. Completing a measurement or exposing a missing measurement can create the ability to make further progress. It never requires a specified accuracy, improvement or increase/decrease of a parameter.

### A concrete discovery loop

1. Choose available material, its exact identity/range, a question and a bounded budget.
2. Record the settings, starting state and what can actually be observed.
3. Run only a supported protocol. Capture predictions before the target outcome; retain no-guess and tie cases.
4. Record correct/eligible counts, prediction coverage and cost separately. Missing evidence stays missing.
5. Interpret the result as positive, negative, inconclusive or invalid for the intended claim.
6. Choose the next discriminating measurement. Preserve contradictory observations.

A valid negative result may rule out an option. A valid inconclusive experiment may reveal a measurement needed next. Neither is a failed level. An interrupted or mixed-configuration run may contain useful observations but does not count as a controlled comparison.

### Evidence-driven branches

- Missing predictions or metrics: inspect the measurement before suggesting a tuning change.
- An unchanged-settings replay changes results: record continued learning; investigate starting-state effects.
- Activity accumulates or fades: collect comparable time windows before proposing a decay/exhaustion hypothesis.
- One capacity change raises cost without improving the declared outcome: retain that result; do not reward expansion.
- Runs disagree: preserve both and test reproducibility.
- A local effect reproduces: ask whether it survives another suitable chunk.
- Untouched material and frozen evaluation are available: test a narrowly stated transfer claim.

These are reusable questions, not prescribed optimization directions. The manifest encodes conditional next questions. Values such as `revise-question`, `record-blocker` and `record-scoped-finding` are terminal review actions, not missing quest IDs.

## Materials and implementation boundaries

All musical quest `dataset_refs` are empty and all musical materials are marked `not_published`. The linked curriculum is a reference, not a downloadable training stream. No verified music assets are currently present in this repository's catalog. Repeated-letter pitch demos are generic diagnostics, not authentic curriculum material, and are not used as substitutes here.

[Catalog v3](../catalog-v3.json) contains verified entry IDs `alice-in-wonderland` and `tiny-shakespeare` for optional later text experiments. Their presence was checked at commit `98c5b4fd0e8d7180f16ac49e0a8db92a00aa9ff6`; this publication did not re-download corpus bytes. They are not music lessons or evidence of musical transfer. Existing catalog integrity and licensing rules still apply.

The current implementation does not provide an executable loader/UI for this quest manifest, verified rhythmic event representation, sonification, independent same-start A/B branches or observed-input learning-disabled evaluation. Treat all quest experiments as plans until their individual requirements are implemented and verified. A pitch symbol at a fixed input interval does not establish rhythm learning; a rest must have explicit semantics.

Replay with learning enabled changes the model. Shared learned relations do not become independent experimental branches merely by using separate training slots. A controlled comparison needs identical independent starting snapshots, fixed source/range and conditions except the declared change. Record state and source fingerprints, configurations, seeds when applicable, counts, elapsed work and rollback.

Generalization needs reserved material, overlap checks and verified learning-disabled evaluation of baseline/candidate snapshots. Separate positions of one repeated motif are not independent musical holdout data. If results inform tuning, retire that test from untouched status. No metric or confidence estimate should be invented when the necessary evidence is unavailable.

## Manifest contract

[music-foundations.json](music-foundations.json) is descriptive metadata with its own `schema_version`; it is not a replacement for `catalog.json`, `catalog-v2.json` or `catalog-v3.json`. Consumers must honor `executable: false`, `runtime_status: planned` and missing material references. Source milestones and Brain adaptation fields are deliberately separate. There is no automatic training, unlock enforcement or runtime compatibility promise.

Before enabling a quest: resolve licensed material; pin its revision and exact byte hash; define event, duration, pitch and rest semantics; test the required observations; and verify the comparison isolation needed for that specific claim.
