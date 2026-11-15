# Serbian text-to-speech demo (VibeVoice 7B fine-tune)

**Listen to the results: https://davidrosic.github.io/mms-tts-demo/**

Audio samples from a Serbian text-to-speech model, made by fine-tuning [VibeVoice](https://github.com/microsoft/VibeVoice) 7B. This is the speech-synthesis part of my master's thesis on automatic Serbian dubbing of video.

## The model

- **Base model:** VibeVoice 7B, with an additional 690 million parameters fine-tuned on top of it.
- **Training data:** 123,914 clips of spontaneous Serbian speech recorded in real conditions, 3 to 10 seconds each, 272.73 hours in total.
- **How the data was made:** a heavily modified Emilia-Pipe (from [Amphion](https://github.com/open-mmlab/Amphion)) that can transcribe and evaluate Serbian on recordings many hours long.
- **Checkpoints:** the demo lets you compare the untouched base model, the checkpoints after epochs 1 to 5, and the final checkpoint.

## What's in the demo

- **7 reference voices.** Four speak English (Alice, Carter, Frank, Maya) and three speak Serbian (Ivan, Normal, Slow). Reference clips range from 3 to 28 seconds.
- **3 sentence lengths:** short, medium and long, in `sentence_files/`.
- **Prefill on/off.** Prefill controls whether the reference voice's timbre is carried into the output.
- **Checkpoint comparison.** For each voice and setting you can play the base model, epochs 1–5 and the last epoch side by side.

Things to listen for: background music, similarity to the reference voice, timbre transfer with prefill on, naturalness, and artifacts.

## Layout

| Path | Contents |
|---|---|
| `index.html` | The demo page (Serbian text, Tailwind CSS, audio loads on click) |
| `voices/samples/` | The 7 reference clips |
| `voices/demo/<checkpoint>/` | Generated audio for `base`, `1stEpoch` … `5thEpoch`, `LastEpoch` |
| `sentence_files/` | The three test sentences |

The page is in Serbian because it accompanies the thesis. Only the demo outputs are published here, not the model weights or the training data.
