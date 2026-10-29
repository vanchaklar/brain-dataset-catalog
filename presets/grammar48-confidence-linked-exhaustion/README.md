# Confidence-linked exhaustion

Higher confidence prolongs exhaustion through 3+6*confidence with exhaustion feedback disabled; activity confidence-penalty score unchanged. Confirmation 65.25% accuracy, 97.32% coverage and 51.49% macro recall versus supplied 63.01%, 97.60% and 48.04%. Graph 3333 composites, 1535 Lonely, 24582 relations, 2723 retries. Actual final exhaustion time 6.079 seconds because adaptation is slow. Experimental grammar result, not a dialogue recommendation.

Synthetic 48-word grammar only, at one second per input. These are external benchmark results, not measurements of the user's current model. Do not transfer these scores to Schema-Guided Dialogue.

Fresh model trained on 34,392 characters. Selection: 10,356; confirmation: 10,362. Graph frozen during evaluation; clocks continue adapting to completed past outcomes. Confirmation is a reused research holdout, not a globally untouched test. No claim of statistical significance or universal best.

See scores.json for exact counts, configuration.json for the complete settings, and provenance.json for hashes. Applying to existing state may behave differently.
