# Budget + adaptive activity, 1-second grammar experiment

These are **tested configurations, not universal “best” settings**. The only changed parameter is `composite_recognition_increment` (1, 2 or 4). Use `scores.json` for exact counts, not the rounded percentages below. `incrementN.json` contains the complete app configuration; the **1,000,000 µs input cadence** is an additional required run condition.

## Scores

| Increment | Selection correct / inputs | Selection letter accuracy | Prediction coverage | Lonely / composites after training | Composite→composite learned edges |
|---|---:|---:|---:|---:|---:|
| 1 (code101 historical preset) | 4,266 / 10,356 (41.19%) | 28.13% | 100% | 324 / 326 | 1 |
| 2 (unsuccessful accuracy tradeoff) | 3,300 / 10,356 (31.87%) | 19.79% | 100% | 168 / 561 | 829 |
| 4 (selected candidate) | 6,549 / 10,356 (63.24%) | 57.87% | 98.73% | 1,557 / 3,319 | 11,245 |

Increment4 was locked before a separate 10,362-character confirmation comparison:

| Increment | Confirmation correct / inputs | Letters correct / letters | Prediction coverage | No prediction |
|---|---:|---:|---:|---:|
| 1 | 4,223 / 10,362 (40.75%) | 2,248 / 8,219 (27.35%) | 100% | 0 |
| 4 | 6,616 / 10,362 (63.85%) | 4,788 / 8,219 (58.26%) | 98.81% | 123 |

Increment2 was not selected and was not evaluated on the separate confirmation split. Its worse accuracy remains recorded rather than silently omitted.

## Conditions and interpretation

- Synthetic 48-word grammar, not the repository's Alice, Shakespeare or large tokenized datasets. Train: 34,392 characters / 448 sentences; selection: 10,356 / 134; confirmation: 10,362 / 135. Exact byte hashes are in `provenance.json`.
- Fresh empty model, one training pass, no state reset at the split, graph-frozen evaluation. Activity controller adapts only from completed past outcomes; this is not a fully frozen dynamical state.
- The confirmation split has zero sentence overlap with training or selection and was not used to choose among these increments. It had been used in earlier, unrelated pruning research: “separate confirmation” does **not** mean globally never used.
- Accuracy denominator includes every character, including spaces and punctuation. Abstentions and ties do not count as correct. Letter accuracy is reported separately.
- Increment1 reproduces the historical 4,266/10,356 score but is a poor composite-connectivity preset. The old preset was chosen retrospectively for overall accuracy from a 36-cell historical study; that was not evidence of useful composite participation.
- Increment4 improves both measured accuracy and connectivity in this comparison, but 46.91% of composites are still Lonely. It creates a much larger graph and incurred 2,831 temporary admission retries per run, versus zero for increments1/2. These are costs, not hidden failures or dropped-input counts. Device latency, battery and memory have not been benchmarked here.
- Strongest composite contributor counts on selection: 0, 371, 6,575 respectively; on confirmation: 0 and 6,503 for increments1/4. This describes prediction contributions, not proof of causal semantics.
- No claim of statistical significance, cross-dataset generalization, best settings for every metric, or superiority on other builds/cadences. Default Confidence is not independently measured by this score package and must not be confused with accuracy.

A composite is **Lonely** if it has no stored relation to a distinct composite node. Either direction and either supported relation kind counts, with no magnitude threshold, before display filtering/level-of-detail. All composite-to-composite edges in these runs were `event_step`.

Both native confirmation processes exited successfully. The actual-JNI fresh-training process also exited successfully: all 34,392 inputs accepted, with 2,830 temporary retries (runner: 2,831). Its complete concepts and relations matched the deterministic runner, not merely their counts.

## Configuration and compatibility

Forward formula `b*w`, relation formula `source_activity*target_activity`, activity adaptation and feedback enabled with `ratio*interval`, original accuracy/mismatch/coverage objective; exhaustion adaptation, pruning and spikes disabled. The full files retain every parameter, including historical schema fields. `prediction_threshold=0.8` is inert legacy metadata, not an active prediction gate.

These files preserve tested settings, not a newly imposed storage policy. No existing app preferences or presets are changed by publishing them. Android UI preferences in the complete configuration are compatibility choices; the native evaluator did not test every Android preference as a performance variable. This catalog does not yet provide automatic app discovery/import of these presets.

## Evidence and limitations

`provenance.json` records source commit, native header hashes, evaluator/binary hashes, split hashes, protocol and command template. `scores.json` includes hashes of the full raw result and trained checkpoint evidence without distributing corpus text, trained graphs or application source. Public hashes establish identity, not independent reproducibility: the full runner and split artifacts are not included in this metadata-only repository. Source commit refers to the code101 research checkout; it is not a claim that the Brain commit has been publicly published.

Only metadata, configurations and aggregate findings are included. Dataset catalogs remain unchanged. No corpus, private runtime state, signing material or credentials are included.
