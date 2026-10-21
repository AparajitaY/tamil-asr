# Tamil Automatic Speech Recognition

Tamil automatic speech recognition using OpenAI Whisper-tiny,
with Common Voice Tamil fine-tuning, FLEURS evaluation,
and FP32/INT8 ONNX export using sherpa-onnx.

## Repository Structure

```text
android_source/       Android application source, when supplied
apk/                  Compiled Android application, when supplied
demo/                 Screenshots, recordings, and sample media
model_and_results/    Model artifacts, configurations, and results
tamilASR.ipynb         Training, evaluation, and export notebook
requirements.txt      Python dependencies
```

## Project Workflow

1. Evaluate pretrained Whisper-tiny on Tamil speech.
2. Fine-tune with a Common Voice Tamil subset.
3. Compare baseline and fine-tuned transcription results.
4. Export FP32 and INT8 ONNX models.
5. Evaluate accuracy, model size, and decoding performance.

The notebook configures 1,000 training examples, 100 validation
examples, and evaluation on the first 200 Tamil FLEURS test examples.

## Getting Started

Install the Python dependencies:

```bash
pip install -r requirements.txt
```

Open `tamilASR.ipynb` in Google Colab with a GPU runtime.
Provide the Common Voice Tamil subset and update dataset,
Google Drive, checkpoint, and output paths as needed.

Some notebook cells require previously generated feature caches
or saved checkpoints. Dependencies are unpinned and the environment
has not been independently validated.

## Evaluation

Metrics include Word Error Rate (WER), Character Error Rate (CER),
model size, decoding time, and real-time factor (RTF).
Saved results are recorded experiment outputs, not independently
reproduced benchmarks.

## Artifacts

Only available files are included. Directories containing only
`.gitkeep` are placeholders. Large binaries are tracked with Git LFS.

If this ZIP supplied its own README or requirements file, the
root-level originals are preserved under
`model_and_results/original_docs/`.

## Acknowledgements

OpenAI Whisper, Hugging Face, Common Voice Tamil,
Google FLEURS, and sherpa-onnx.
Third-party licenses and dataset terms apply.
