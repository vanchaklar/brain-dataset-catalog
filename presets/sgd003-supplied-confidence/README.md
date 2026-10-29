# SGD003 supplied confidence reference

Reference configuration. Confirmation47.99% overall accuracy,97.98% coverage; USER49.87%,SYSTEM46.58%. Average prior512 USER-only confidence27.15%.10324 composites,5038 Lonely,69256 relations. Training+selection15110 admission retries.

Deterministic seed20261029 shuffle of whole dialogues:90train,19selection,19confirmation. One fresh training pass; Unicode scalar replay USER=token,SYSTEM=observed-output; annotations excluded, no delimiters inserted. Episode replay context resets, graph frozen during evaluation, adaptive clocks continue from completed past inputs. Confirmation restores identical trained checkpoint, not selection-end state. No Android scheduler or user phone state benchmark.

Disjoint dialogue IDs.28/248 confirmation utterances exactly occurred in training (631/13931 characters), mostly natural shared boilerplate; not phrase-disjoint or unseen-domain evaluation.

One deterministic shard split; accuracy is character prediction, not dialogue quality/task success. Confidence excludes SYSTEM output. No universal ranking. Published metadata excludes corpus, per-input decisions, trained state and runner source.

See scores.json for exact counts and role metrics; provenance.json for source, split identities and hashes.
