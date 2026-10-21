# Tamil Automatic Speech Recognition

Tamil ASR experiments using OpenAI Whisper-tiny, Common Voice Tamil
fine-tuning, FLEURS evaluation, and ONNX export for Android deployment.

## Project Structure

- `android_source/` — Android application source, when supplied.
- `apk/` — Android application package, when supplied.
- `demo/` — Demonstration media and sample assets.
- `model_and_results/` — Model artifacts, configurations, and results.
- `tamilASR.ipynb` — Training, evaluation, and export notebook.
- `requirements.txt` — Notebook-derived Python dependencies.

## Approach

1. Evaluate pretrained Whisper-tiny on Tamil speech.
2. Fine-tune with a Common Voice Tamil subset.
3. Compare baseline and fine-tuned results on Tamil FLEURS.
4. Export FP32 and INT8 ONNX models using sherpa-onnx.
5. Examine transcription accuracy, model size, and decoding speed.

The notebook configures 1,000 training examples, 100 validation examples,
and evaluation on the first 200 FLEURS test examples.

## Setup

```bash
pip install -r requirements.txt
```

Open `tamilASR.ipynb` in Google Colab with a GPU runtime. Supply the
Common Voice Tamil subset and update Drive, dataset, and checkpoint paths.
Some cells require previously generated caches or checkpoints.

## Evaluation

Metrics include Word Error Rate (WER), Character Error Rate (CER),
model size, decoding time, and real-time factor (RTF).
Saved results are experiment outputs and have not been independently rerun.

## Artifacts

Only supplied files are included. Directories containing only `.gitkeep`
are placeholders. Large binary artifacts use Git LFS.

## Acknowledgements

OpenAI Whisper, Hugging Face, Common Voice, Google FLEURS, and sherpa-onnx.
Third-party model and dataset terms apply.
