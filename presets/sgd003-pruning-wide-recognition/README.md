# SGD003 pruning and wider recognition

Pruning enabled, recognition pairs8/context6. Confirmation49.36% accuracy versus reference47.99%, but coverage97.80% versus97.98%. USER49.05% versus49.87%; SYSTEM49.59% versus46.58%. Average prior512 USER-only confidence25.19% versus27.15%.3891 composites,807 Lonely;79486 relations versus69256, so fewer nodes does not mean fewer relations. Training+selection15207 admission retries versus15110. Tradeoff, not an across-the-board improvement. Pruning does not remove existing Lonely nodes when applied to an already-trained model.

Deterministic seed20261029 shuffle of whole dialogues:90train,19selection,19confirmation. One fresh training pass; Unicode scalar replay USER=token,SYSTEM=observed-output; annotations excluded, no delimiters inserted. Episode replay context resets, graph frozen during evaluation, adaptive clocks continue from completed past inputs. Confirmation restores identical trained checkpoint, not selection-end state. No Android scheduler or user phone state benchmark.

Disjoint dialogue IDs.28/248 confirmation utterances exactly occurred in training (631/13931 characters), mostly natural shared boilerplate; not phrase-disjoint or unseen-domain evaluation.

One deterministic shard split; accuracy is character prediction, not dialogue quality/task success. Confidence excludes SYSTEM output. No universal ranking. Published metadata excludes corpus, per-input decisions, trained state and runner source.

See scores.json for exact counts and role metrics; provenance.json for source, split identities and hashes.
