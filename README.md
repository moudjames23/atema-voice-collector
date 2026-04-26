# atema-voice-collector

Flutter app for collecting **French voice recordings of Conakry quartier names** from drivers and testers. The dataset feeds the offline STT exploration in [`atema-mobile#71`](https://github.com/moudjames23/atema-mobile/issues/71) — fine-tuning Whisper / Vosk against accented Guinean French + motorcycle ambient noise.

## Status

🅿️ **Parked — design only, no implementation yet.**

Spike of `atema-mobile#71` (Vosk + Whisper baseline) returned a useful but incomplete signal: Whisper is viable on TTS clean French (66 % Top-1) but the real question — Conakry French + moto noise — needs real audio. Until we have a reason to commit the 6–8 days of build work, the design lives here and we collect ad-hoc (smartphone recorder + WhatsApp/Drive sharing).

See [issue #1](https://github.com/moudjames23/atema-voice-collector/issues/1) for the MVP spec.

## When this gets built

Trigger conditions to start implementation:

1. The first round of ad-hoc recordings shows Whisper hits ≥ 50 % Top-1 on real Conakry voices.
2. We commit to fine-tuning a STT model rather than relying on cloud STT + matcher fallback.
3. We have ≥ 5 recruited testers willing to spend 15-20 min each.

If any of those is missing, this app stays parked and we keep using cloud STT + the [`alias_matcher`](https://github.com/moudjames23/atema-mobile/blob/main/lib/features/destinations/domain/alias_matcher.dart) for the residual.

## Related

- [`atema-mobile`](https://github.com/moudjames23/atema-mobile) — main driver app
- [`atema-web`](https://github.com/moudjames23/atema-web) — backend, will host the collector sync endpoints
- [`atema-mobile#67`](https://github.com/moudjames23/atema-mobile/issues/67) — alias matcher (closed)
- [`atema-mobile#69`](https://github.com/moudjames23/atema-mobile/issues/69) — STT shortlist unification (closed)
- [`atema-mobile#71`](https://github.com/moudjames23/atema-mobile/issues/71) — offline STT exploration (parked)
