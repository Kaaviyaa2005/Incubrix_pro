# Engineering report — current prototype status

## Approach
The application uses FastAPI for HTTP endpoints, a browser editing UI, FFmpeg/FFprobe for video normalisation and muxing, edge-tts for script narration, and faster-whisper for speech transcription. Local clip candidates are ranked with filename/category token overlap and a category prior. Captions are emitted as SRT and optionally burned into the MP4.

## Changes in this revision
- Added browser microphone recording through MediaRecorder.
- Audio-only submissions no longer require the user to type a transcript; the backend transcribes with faster-whisper.
- The Preview step renders the same styled, narrated video as the final output so the selected caption settings and narration audio are present.
- Added audio-duration validation (10 minutes), structured error payloads for several input failures, health/readiness aliases, and an expanded manifest.

## Known limitations
This is not yet a fully compliant assessment submission. Keyword/category matching is not semantic understanding and cannot establish that footage matches abstract lines. The local asset licence metadata is unverified. Scene timing is proportional to word count, not forced alignment. The render endpoint is synchronous and has no idempotency, durable queue, S3-compatible storage, provider fallback, callback signature, or correlation-ID logging. Multiple aspect ratios are requested one at a time. There is no independent vision-language relevance model or verified 85% human-rating result. No performance or cost benchmark is reported because it has not been measured.

## Metrics to collect (not measured here)
Run the batch runner over ten diverse inputs and record cold/warm turnaround for 60 seconds of narration, cost per output minute, coverage, per-scene human relevance ratings, render success rate, repeat-clip rate, peak memory and GPU time. Preserve failed runs. Do not enter fabricated numbers in the Submission Form.

## Submission recommendation
Treat this build as a development prototype. Before claiming assessment compliance, complete the remaining items in README.md, verify commercial rights for every clip, run a repeatable test pack, deploy a protected/rate-limited demo, and have the candidate explain the full code path.
