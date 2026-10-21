# Tamil Automatic Speech Recognition

Tamil speech recognition using OpenAI Whisper-tiny, fine-tuned on Common Voice Tamil and evaluated on Tamil FLEURS. The project includes model conversion and FP32/INT8 ONNX evaluation using sherpa-onnx, with directories for Android source and demonstration assets.

## Highlights

- Baseline and fine-tuned Whisper-tiny transcription.
- Common Voice Tamil fine-tuning with 1,000 configured training examples and 100 validation examples.
- Evaluation on the first 200 Tamil FLEURS test examples.
- FP32 and INT8 ONNX export for deployment experiments.
- Accuracy, model-size, and decoding-performance comparisons.

## Repository Structure

```text
android_source/       Android source directory
 demo/                Demonstration assets
model_and_results/
  checkpoints/        Checkpoint artifacts
  finetuned/          Fine-tuned model artifacts
  huggingface_checkpoint/  Hugging Face checkpoint artifacts
  evaluation/         Evaluation artifacts
  fleurs_evaluation/  FLEURS evaluation artifacts
  onnx_exports/       ONNX export artifacts
  sherpa_onnx/        sherpa-onnx artifacts
  whisper-tamil-int8/ INT8 deployment artifacts
  original_docs/      Documentation supplied with project archives
tamilASR.ipynb         Training, evaluation, and export notebook
requirements.txt      Python dependencies
```

## Setup

```bash
git clone [https://github.com/AparajitaY/tamil-asr.git](https://github.com/AparajitaY/tamil-asr.git)
cd tamil-asr
pip install -r requirements.txt
```

Some large artifacts may require Git LFS. If your checkout contains LFS pointer files rather than model binaries, install Git LFS and run:

```bash
git lfs install
git lfs pull
```

## Running the Notebook

Open [tamilASR.ipynb](tamilASR.ipynb) in Google Colab and enable a GPU runtime for fine-tuning.

1. Provide the Common Voice Tamil subset containing `ta/train.tsv`, `ta/dev.tsv`, and `ta/clips/`.
2. Update the dataset, Google Drive, checkpoint, and output paths.
3. Run the relevant preprocessing, training, evaluation, and export cells.

Some cells depend on previously generated feature caches or saved checkpoints. A fresh run may require adjusting the preprocessing order. Dependencies are unpinned; the environment has not been independently validated.

## Evaluation

The notebook compares baseline and fine-tuned models and evaluates exported FP32/INT8 models using:

- Word Error Rate (WER).
- Character Error Rate (CER).
- Model size.
- Decoding time and real-time factor (RTF).

See [model_and_results](model_and_results/) for the uploaded artifacts. Saved outputs represent recorded experiments, not independently reproduced benchmarks. Compare results only when sample selection, text normalization, and decoding settings match.

## Android APK

Check the [Releases page](https://github.com/AparajitaY/tamil-asr/releases) for published application packages. APK availability depends on whether a release has been uploaded. If an APK is distributed inside a ZIP or 7z archive, extract the `.apk` before installation.

## Acknowledgements

OpenAI Whisper, Hugging Face Transformers and Datasets, Common Voice Tamil, Google FLEURS, and sherpa-onnx. Third-party licenses and dataset terms apply.
