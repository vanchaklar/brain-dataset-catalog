# Pure confidence scores

Both automatic clocks use confidence alone as their score; original tau expressions retained. Confirmation 62.71% accuracy, 98.45% coverage and 48.02% macro recall versus supplied 63.01%, 97.60% and 48.04%. Coverage gain with a small accuracy loss. 3305 composites, 1559 Lonely, 24015 relations, 2528 retries. Exhaustion still recorded zero feedback updates and five discarded comparisons; neither coverage guard fired. Experimental grammar result, not a dialogue recommendation.

Synthetic 48-word grammar only, at one second per input. These are external benchmark results, not measurements of the user's current model. Do not transfer these scores to Schema-Guided Dialogue.

Fresh model trained on 34,392 characters. Selection: 10,356; confirmation: 10,362. Graph frozen during evaluation; clocks continue adapting to completed past outcomes. Confirmation is a reused research holdout, not a globally untouched test. No claim of statistical significance or universal best.

See scores.json for exact counts, configuration.json for the complete settings, and provenance.json for hashes. Applying to existing state may behave differently.
