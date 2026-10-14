# Version 3: large tokenized sources

`catalog-v3.json` is additive. `catalog.json` and `catalog-v2.json` retain their previous bytes and contracts. Clients must explicitly support each declared format and replay mode, rejecting unknown values rather than treating a binary shard as UTF-8 text.

## Choices and sizes

The five existing text/conversation/terminal choices are retained unchanged. Four training shards are added: three FineWeb-Edu GPT-2 shards and one FineWeb Classic GPT-2 shard. Each contains 100,000,000 token IDs and occupies 200,001,024 bytes (about 190.74 MiB). These are four shards from two related corpus selections, not four independent datasets; overlap is possible. Two validation assets are in the separate `evaluation_assets` section and must never appear in the normal Train queue. The catalog does not itself enable an evaluation workflow.

Each source row exposes two replay modes over the same pinned asset: `token_ids` and `token_text_then_id`. Clients should share the verified source download and tokenizer across modes, while preserving the selected replay mode in saved training configuration.

## Binary and tokenizer contract

Format `llmc-gpt2-token-shard-v1` contains 256 little-endian int32 header values: magic 20240520, version 1, token count, and zero reserved fields. Payload IDs are unsigned little-endian uint16 values. Check the exact downloaded byte length and SHA-256, header fields/count, all ID ranges and absence of truncation/trailing bytes before activation. Stream the asset rather than loading 100 million IDs into memory. A partial or failed download must never become an active source.

The vocabulary has 50,257 IDs and is pinned by revision, URL, byte length and SHA-256. Verify it before decoding. Namespace token identities using the tokenizer fingerprint and validated stream identity. GPT-2 vocabulary strings use a byte-to-Unicode mapping; reverse that mapping before strict UTF-8 decoding. Do not train the display glyphs as if they were the original text.

## Replay and boundaries

Token-only mode uses actual token IDs. Text-plus-ID mode emits decoded Unicode characters followed by the associated original IDs, preserving their order. Some pieces split a UTF-8 codepoint: accumulate complete token pieces until strict UTF-8 can finish, then emit that group's characters and its ordered IDs. Never replace malformed bytes, invent readable escape tokens or emit raw-byte concepts. Character and ID cue identities remain distinct.

ID 50256 is a structural document delimiter, not ordinary printed `<|endoftext|>` text. Physical shard boundaries may cut documents; do not claim they are natural document boundaries. The selected shards have checked outer UTF-8 boundaries, but their first/last document can be partial. Saved cursors/configuration must preserve mode, source/tokenizer identities, token/group/phase position and boundary policy so resume neither duplicates nor drops text or cues. The app adapter's validated cursor and migration rules govern execution.

## Integrity, provenance and licensing

URLs/revisions, exact lengths, publisher Git-LFS SHA-256 values, tokenizer hashes, attribution and source/license links are metadata in the catalog. Bounded header, prefix/suffix and tokenizer checks were performed when preparing the entries. This was not a complete download/hash verification of every 200 MB shard; clients must validate the complete download. CDN/Xet ETags are not substitutes for file SHA-256.

FineWeb source licenses and attribution obligations remain with their publishers; this catalog neither relicenses nor redistributes the corpora. Review each entry's source and license links before use. FineWeb Classic includes publisher filtering/provenance notes; use those rather than assuming every FineWeb derivative has identical contents or terms.

This public repository contains metadata only: no Brain implementation, corpus samples, tokenizer copies, trained graphs, private checkpoints or credentials. Large size is not evidence of model quality or device capacity; training performance and memory requirements depend on the client and learned graph.
