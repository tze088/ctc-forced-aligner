# About this fork

Fork of [MahmoudAshraf97/ctc-forced-aligner](https://github.com/MahmoudAshraf97/ctc-forced-aligner),
branched at `11855d1de76af2b490dd2e8e2db2661805ae90a0` on `19/8/2026`. **Upstream is the one you probably want.**

Not tracking upstream.

## Why

We supply our own audio and text preprocessing, so the I/O stages and their
dependencies (`torchcodec`, `uroman`, `nltk`, `unidecode`, plus `ffmpeg`)
are removed.

## Changes

- Removed `load_audio()`. Pass a 1-D mono float waveform at 16 kHz, `[-1, 1]`,
  already on the model's device and dtype.
- Removed the `align.py` CLI and its `ctc-forced-aligner` entry point.
- Removed `text_utils.py`.
- Runtime deps trimmed to `torch`, `transformers`.

## What we use

`load_alignment_model` → `generate_emissions` → `get_alignments` → `get_spans`.

## License

Upstream ships **no `LICENSE` file**. The grant is this line from the upstream
README, reproduced verbatim:

> This project is licensed under the BSD License, note that the default model
> has CC-BY-NC 4.0 License, so make sure to use a different model for commercial
> usage.