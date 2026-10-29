# Compact graph, continuation pruning

Same confidence clocks as supplied, with known-continuation pruning enabled. Confirmation 61.73% accuracy and 96.82% coverage: a 1.28 percentage-point accuracy cost versus reference. Graph shrinks to 946 composites, 204 Lonely and 11691 relations, with zero admission retries. Compact tradeoff, not an accuracy improvement.

Synthetic 48-word grammar only, at one second per input. These are external benchmark results, not measurements of the user's current model. Do not transfer these scores to Schema-Guided Dialogue.

Fresh model trained on 34,392 characters. Selection: 10,356; confirmation: 10,362. Graph frozen during evaluation; clocks continue adapting to completed past outcomes. Confirmation is a reused research holdout, not a globally untouched test. No claim of statistical significance or universal best.

See scores.json for exact counts, configuration.json for the complete settings, and provenance.json for hashes. Applying to existing state may behave differently.
