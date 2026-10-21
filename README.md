# Tamil Automatic Speech Recognition

A Tamil automatic speech recognition (ASR) project using OpenAI Whisper-tiny. It explores fine-tuning on Common Voice Tamil, evaluation on the Tamil FLEURS dataset, and ONNX export for potential Android deployment.

## Overview

The project covers:
- Baseline Tamil transcription using pretrained Whisper-tiny.
- Fine-tuning with a Common Voice Tamil subset.
- Comparison of baseline and fine-tuned transcription results.
- Export and evaluation of FP32 and INT8 models using sherpa-onnx.
- Organization of Android source, APK, and demonstration assets.

## Repository Structure

```text
android_source/       # Android application source
apk/                  # Compiled Android application
demo/                 # Screenshots and demo recordings
model_and_results/    # Model artifacts and evaluation results
README.md             # Project documentation
requirements.txt      # Python dependencies
tamilASR.ipynb         # Training, evaluation, and export notebook
```

## Model and Dataset

| Component | Details |
|-----------|---------|
| Base model | OpenAI Whisper-tiny |
| Language | Tamil |
| Fine-tuning data | Common Voice Tamil subset |
| Configured training subset | 1,000 examples |
| Configured validation subset | 100 examples |
| Evaluation data | First 200 Tamil FLEURS test examples |
| Export formats | FP32 and INT8 ONNX |

## Getting Started

Install the Python dependencies:

```bash
pip install -r requirements.txt
```

Open `tamilASR.ipynb` in Google Colab and enable a GPU runtime for fine-tuning.

Before running:
1. Provide `common_voice_tamil_subset.zip` in Google Drive.
2. Ensure the extracted dataset contains `ta/train.tsv`, `ta/dev.tsv`, and `ta/clips/`.
3. Update the dataset, checkpoint, and output paths as needed.

Some notebook cells depend on previously generated feature caches or saved checkpoints and may need adjustment for a fresh run.

## Evaluation

The notebook measures:
- Word Error Rate (WER).
- Character Error Rate (CER).
- Exported model size.
- Decoding time and real-time factor (RTF).

Baseline and fine-tuned models are evaluated on the same selected FLEURS examples. Exported FP32 and INT8 models are also evaluated to examine accuracy, size, and runtime trade-offs.

## Android Deployment

The repository reserves directories for Android source code, a compiled APK, and demonstration media. Android build and installation instructions will be added when those artifacts are available.

## Project Status

The experiment notebook is available for repository upload. Android source, APK, demo assets, and standalone model files are pending upload.

## Acknowledgements

- OpenAI Whisper
- Hugging Face Transformers and Datasets
- Common Voice Tamil
- Google FLEURS
- sherpa-onnx
