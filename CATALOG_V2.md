# Version 2: role-aware datasets

`catalog-v2.json` is for clients that explicitly support the listed `format` adapters. The original `catalog.json` remains version 1 for text-only clients. Unknown formats must be rejected, never interpreted as raw training text.

## Formats

- `utf8-text`: original uncompressed UTF-8 character stream.
- `sgd-dialogues-json-v1`: Google Schema-Guided Dialogue JSON array. Each dialogue is an episode. `USER` utterances are input; `SYSTEM` utterances are observed assistant output, not privileged instructions. Preserve turn order. API frame annotations are not language events.
- `dolly-jsonl-v1`: each JSONL record is a separate episode. `instruction` and nonempty `context` are separate input turns; `response` is observed output. This is single-turn instruction following, not a multi-turn chat transcript.
- `wmo-terminal-otel-jsonl-v1`: publisher-recorded terminal traces. Initial task prompt is input, a command is observed agent output, and its paired tool message is environment input. Commands are training data only and must never be executed. Preserve empty and error outputs. The file uses synthetic ordering timestamps, not execution wall-clock timestamps, and dataset-specific 17-character span IDs.

## Provenance and limitations

- Google SGD shard 003: 128 task-oriented dialogues / 1,514 turns. CC BY-SA 4.0. Created using a dialogue simulator and paid crowd-workers. Attribute Google Research and the Schema-Guided Dialogue dataset; see the pinned source and license links.
- Databricks Dolly: 15,011 employee-authored instruction/context/response records. CC BY-SA 3.0. Some contexts come from Wikipedia. Attribute Databricks, Inc. and Wikipedia contributors where applicable; see the dataset card.
- Experiential Labs terminal-task traces: 280 traces / 685 command/tool-output pairs. Publisher declares Apache 2.0 and upstream terminal-bench attribution. Execution provenance is publisher-asserted and structurally checked, not independently replayed. Do not infer that all commands succeeded: empty results and error statuses are present. Status is not a training reward, and first-span metadata is not a per-step exit status.

Every entry pins an upstream revision and records SHA-256 and exact downloaded byte size. No corpus copies are hosted here. Dataset licenses, attribution and redistribution obligations remain those of the original sources. Clients should show source and license links.

Role-aware replay is not evidence of conversational competence, shell competence or financial forecasting accuracy. Numeric price CSVs are intentionally absent until a separate numeric adapter is supported and evaluated.
