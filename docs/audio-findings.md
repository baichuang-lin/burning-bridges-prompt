# What I measured about the vendor and audio

The prompt says "the supplied track is the only audio". Making that true took two
paid renders and one measurement, and the answer is that the track is attached to
the finished file rather than requested from the model.

Measured 2026-10-13 on kie.ai, model `bytedance/seedance-2-5`, 480p, 20 seconds.

| Question | Answer |
| --- | --- |
| Does `reference_audio_urls` pass a track through? | **No.** With `generate_audio: false`, the returned file has **no audio stream at all**. |
| With `generate_audio: true`, does the model use the supplied recording? | **Yes** — correlation **0.897** against the supplied file, so it is that recording rather than invented music. |
| Does it start at the top of the file? | **No** — the music starts about **2.1 seconds in**. |
| What does attaching it locally give? | Correlation **1.000** at zero offset. |

Method: downmix to 8 kHz mono, measure loudness in 100 ms frames (an envelope, not
the waveform, so a lossy re-encode or a small offset does not hide a match), then
cross-correlate over a ±8 s window. A synthetic noise bed is the negative control
for the same metric and scores 0.07.

## What follows from it

- Every render is requested with `generate_audio: false`, so the model cannot mix
  invented music underneath the track.
- The prompt states the rule in words as well, because the instruction and the
  request should agree rather than contradict each other.
- The finished file gets the track attached from its first sample, with the video
  stream copied untouched — `-map 0:v:0 -map 1:a:0`, so a file that already carries
  sound cannot end up with two audio streams.
- The track is *also* sent as a reference audio, because the vendor bills reference
  audio at no extra cost and it does no harm.

## What this does not say

It says nothing about how a reference audio *sounds*; only that the returned audio
is the supplied recording, shifted. If you would rather trust the vendor for sound,
turn `generate_audio` on and expect the offset. If you need the music from 0.000s,
attach it yourself.
