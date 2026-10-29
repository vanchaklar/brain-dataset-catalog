# Pruning with wider recognition

Known-continuation pruning enabled, recognition pair limit 8 and composite context cap 6; supplied confidence clocks unchanged. Confirmation 65.72% accuracy, 96.54% coverage and 52.45% whole-evaluation macro recall versus supplied 63.01%, 97.60% and 48.04%. Graph 1110 composites, 157 Lonely (14.14%), 23774 relations, 2050 retries. Higher accuracy and fewer Lonely composites, but lower coverage. Single grammar study, not a dialogue recommendation or universal best.

Synthetic 48-word grammar only, at one second per input. These are external benchmark results, not measurements of the user's current model. Do not transfer these scores to Schema-Guided Dialogue.

Fresh model trained on 34,392 characters. Selection: 10,356; confirmation: 10,362. Graph frozen during evaluation; clocks continue adapting to completed past outcomes. Confirmation is a reused research holdout, not a globally untouched test. No claim of statistical significance or universal best.

See scores.json for exact counts, configuration.json for the complete settings, and provenance.json for hashes. Applying to existing state may behave differently.
