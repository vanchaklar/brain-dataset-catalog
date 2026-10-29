# Accuracy focus, fixed 3s exhaustion

Activity uses the original accuracy/mismatch/coverage score; exhaustion is fixed at 3 seconds. Confirmation 64.50% accuracy, 98.50% coverage and 48.09% macro recall. Versus the supplied reference this improves accuracy, but raises Lonely fraction to 49.04%, relations to 31916 and admission retries to 5262. Not a confidence-score winner or universal best.

Synthetic 48-word grammar only, at one second per input. These are external benchmark results, not measurements of the user's current model. Do not transfer these scores to Schema-Guided Dialogue.

Fresh model trained on 34,392 characters. Selection: 10,356; confirmation: 10,362. Graph frozen during evaluation; clocks continue adapting to completed past outcomes. Confirmation is a reused research holdout, not a globally untouched test. No claim of statistical significance or universal best.

See scores.json for exact counts, configuration.json for the complete settings, and provenance.json for hashes. Applying to existing state may behave differently.
