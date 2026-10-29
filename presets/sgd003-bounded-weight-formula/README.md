# SGD003 bounded-weight forward formula

Forward formula b*w/(1+abs(w)), supplied settings otherwise unchanged. Confirmation54.27% accuracy,99.78% coverage and28.91% average prior512 USER-only confidence versus supplied47.99%,97.98%,27.15%. USER52.81%,SYSTEM55.36%. Costs:16102 composites,8574 Lonely(53.25%),93571 relations and21318 fresh training+selection admission retries. Higher prediction metrics but substantially larger graph; not a universal best.

Deterministic seed20261029 shuffle of whole dialogues:90train,19selection,19confirmation. One fresh training pass; Unicode scalar replay USER=token,SYSTEM=observed-output; annotations excluded, no delimiters inserted. Episode replay context resets, graph frozen during evaluation, adaptive clocks continue from completed past inputs. Confirmation restores identical trained checkpoint, not selection-end state. No Android scheduler or user phone state benchmark.

Disjoint dialogue IDs.28/248 confirmation utterances exactly occurred in training (631/13931 characters), mostly natural shared boilerplate; not phrase-disjoint or unseen-domain evaluation.

One deterministic shard split; accuracy is character prediction, not dialogue quality/task success. Confidence excludes SYSTEM output. No universal ranking. Published metadata excludes corpus, per-input decisions, trained state and runner source.

See scores.json for exact counts and role metrics; provenance.json for source, split identities and hashes.
