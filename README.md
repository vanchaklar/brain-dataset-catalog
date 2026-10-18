# Brain dataset catalog

Public metadata for the Brain Android training catalog. This repository contains dataset names, descriptions, external source URLs, licensing provenance, pinned download URLs and integrity metadata only. It contains no Brain application source, corpus copies, trained graphs, credentials or user data.

## Music discovery quest line

See [Music foundations: adaptive discovery](quests/music-foundations.md) and its [machine-readable plan](quests/music-foundations.json). These reference an existing Kodály Center curriculum and distinguish its documented milestones from the proposed Brain experiments. Music materials and runtime support are explicitly marked as planned; this metadata does not make the quests executable.

## Catalog contract

`catalog.json` uses `version: 1` and a `datasets` array. Required fields are `id`, `title`, `description`, `license`, `source_url`, `url`, `sha256`, `size_bytes`, `encoding` and `compression`. `sha256` and `size_bytes` describe the exact downloaded bytes before any decoding or decompression. `uncompressed_size_bytes` describes decoded-container bytes and is required for compressed files. This initial catalog contains uncompressed UTF-8 files only. Additional provenance fields include `license_url`, `repository_url`, `revision`, `language` and an optional `license_notice`.

Every corpus URL is pinned to a complete upstream Git commit, not a moving branch. Clients must verify SHA-256 and size before training and must reject mismatches. Download and decompression limits should be applied independently. Metadata updates cannot silently replace the bytes associated with an existing pinned entry.

## Initial entries

- Alice’s Adventures in Wonderland: Lewis Carroll prose, 173,595 bytes. GITenberg copy of Project Gutenberg ebook 11. Upstream metadata and the official Project Gutenberg ebook page state public domain in the USA. The downloaded file retains the Project Gutenberg notice and full license; those terms and local copyright law apply. The catalog includes the notice and a license link for display.
- Tiny Shakespeare: 1,115,394 bytes of Shakespeare dialogue from Andrej Karpathy’s character-language-model example. The pinned repository README declares MIT; it does not provide a separate dataset-specific license. The catalog reports that declaration accurately rather than implying a new corpus license. The underlying Shakespeare works are public domain.

## Licensing and provenance

Dataset rights remain with their respective sources. The catalog does not relicense or redistribute dataset files and does not claim that public-domain status is identical in every jurisdiction. Review the source and license links before use or redistribution. A Project Gutenberg copy with associated notices remains subject to its stated terms. Integrity and UTF-8 decoding were checked against the exact linked files when these entries were prepared.

Do not upload corpora, private project files, trained models, credentials or user data to this repository.
