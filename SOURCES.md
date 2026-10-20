# Sources and licences

- Local B-roll: files placed by the candidate in `data/stock_clips/`. **The exact origin URL, licence, attribution and commercial-use permission have not been verified by this code.** Before submission, create an asset inventory with one row per clip (filename, source URL, licence URL/name, attribution text, commercial-use permission, proof captured).
- Text-to-speech: `edge-tts` library/service. Review the service terms and chosen voice terms before commercial deployment.
- Speech-to-text: `faster-whisper` (CTranslate2 implementation of Whisper). Model: configurable through `ASR_MODEL`, default `small`; download and model licence should be recorded for the deployed model.
- Video processing: FFmpeg/FFprobe; installed separately by the operator. Verify the installed build and its licensing configuration for your deployment.
- UI fonts: system fonts; Google Fonts are not required by the application logic.
- Do not treat the `Needs verification` value in the media library as proof of a commercial licence.
