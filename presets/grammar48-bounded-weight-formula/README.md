# Bounded-weight forward formula

Forward formula b*w/(1+abs(w)); supplied settings otherwise unchanged. Confirmation 66.71% accuracy, 98.94% coverage and 50.99% whole-evaluation macro recall versus supplied 63.01%, 97.60% and 48.04%. Costs: 5094 composites, 2464 Lonely, 34743 relations and 6071 admission retries. Accuracy/coverage option with substantially higher graph cost; not a dialogue recommendation or universal best.

Synthetic 48-word grammar only, at one second per input. These are external benchmark results, not measurements of the user's current model. Do not transfer these scores to Schema-Guided Dialogue.

Fresh model trained on 34,392 characters. Selection: 10,356; confirmation: 10,362. Graph frozen during evaluation; clocks continue adapting to completed past outcomes. Confirmation is a reused research holdout, not a globally untouched test. No claim of statistical significance or universal best.

See scores.json for exact counts, configuration.json for the complete settings, and provenance.json for hashes. Applying to existing state may behave differently.
