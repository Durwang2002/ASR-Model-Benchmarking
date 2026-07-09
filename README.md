# Comparative Study of Speech-to-Text Models for Noisy Real-World Audio

## Overview

This project presents a comparative evaluation of three Automatic Speech Recognition (ASR) models for speech-to-text transcription.

The study benchmarks the models using the official LibriSpeech test-clean dataset and evaluates their performance using Word Error Rate (WER), inference time, memory usage, and deployment feasibility.

The objective is to identify a suitable ASR model for deployment in a voice-based customer support assistant operating in real-world environments.

---

## Objectives

- Compare state-of-the-art ASR models.
- Benchmark transcription performance on a common evaluation dataset.
- Measure Word Error Rate (WER).
- Measure inference latency.
- Measure memory consumption.
- Analyze deployment feasibility.
- Recommend the most suitable production model.

---

## Models Evaluated

| Model | Description |
|--------|-------------|
| OpenAI Whisper Base | Transformer-based multilingual speech recognition model |
| Faster-Whisper Base | Optimized Whisper implementation using CTranslate2 |
| Facebook Wav2Vec2 Base | Self-supervised transformer model for speech recognition |

---

## Dataset

**Dataset:** LibriSpeech Test-Clean

**Source:** https://www.openslr.org/12

### Dataset Characteristics

- English speech
- Human-verified transcripts
- High-quality recordings
- Standard benchmark dataset for ASR research

### Evaluation Samples

- 30 fixed audio samples
- Same subset used for all models
- Identical evaluation conditions

---

## Methodology

The benchmarking pipeline consists of the following stages:

1. Environment Setup
2. Dataset Preparation
3. Audio Selection
4. Ground Truth Extraction
5. Model Benchmarking
6. Text Normalization
7. Performance Evaluation
8. Comparative Analysis
9. Recommendation
10. Production Deployment Planning

---

## Evaluation Metrics

The following metrics were used for evaluation:

- Word Error Rate (WER)
- Average Inference Time
- Memory Usage
- Setup Complexity
- Deployment Suitability

---

## Benchmark Results

| Model | Average WER | Average Inference Time | Average Memory Usage |
|--------|------------:|-----------------------:|---------------------:|
| Whisper Base | **0.0569** | **1.300 sec** | **3.46 MB** |
| Faster-Whisper Base | 0.0643 | 2.363 sec | 0.91 MB |
| Wav2Vec2 Base | **0.0341** | **1.077 sec** | 52.90 MB |

---

## Comparative Analysis

### Whisper Base

**Strengths**

- Strong transcription quality
- Robust across diverse speech conditions
- Simple deployment
- Mature ecosystem

**Limitations**

- Slightly higher WER than Wav2Vec2 on the evaluation dataset

---

### Faster-Whisper Base

**Strengths**

- Very low memory usage
- Efficient implementation

**Limitations**

- Slower inference on the benchmark environment

---

### Wav2Vec2 Base

**Strengths**

- Lowest Word Error Rate
- Fastest inference
- Strong benchmark performance

**Limitations**

- Higher memory consumption
- Additional validation recommended for noisy production environments

---

## Final Recommendation

Although Wav2Vec2 achieved the best benchmark performance on the LibriSpeech test-clean dataset, the intended deployment scenario involves noisy customer support conversations with multiple accents.

Considering benchmark results together with expected production requirements, Whisper Base is recommended as the most balanced model due to its robustness, deployment simplicity, and suitability for real-world speech recognition applications.

---

## Repository Structure

```
ASR-Model-Benchmarking/
│
├── benchmark_asr_models.ipynb
├── README.md
├── requirements.txt
│
├── data/
│   └── evaluation_dataset.csv
│
├── results/
│   ├── benchmark_results.csv
│   ├── whisper_results.csv
│   ├── faster_whisper_results.csv
│   ├── wav2vec2_results.csv
│   ├── comparison_table.csv
│   └── final_recommendation.csv
│
├── reports/
│   ├── Technical_Report.pdf
│   └── Executive_Summary.pdf
│
├── images/
│   ├── wer_chart.png
│   ├── latency_chart.png
│   ├── memory_chart.png
│   └── comparison_chart.png
│
└── LICENSE
```

---
## Usage

Run the Jupyter Notebook:

```bash
jupyter lab
```

Open:

```
benchmark_asr_models.ipynb
```

Execute the notebook sequentially from the first cell to reproduce all experiments.

---

## Future Improvements

Potential extensions to this work include:

- Evaluation on noisy customer support datasets
- Fine-tuning using domain-specific conversational speech
- GPU-based benchmarking
- Real-time streaming transcription
- Multi-language evaluation
- Speaker diarization
- Confidence score analysis

---

## References

- OpenAI Whisper
- Faster-Whisper
- Facebook AI Research Wav2Vec2
- LibriSpeech Dataset
- JiWER Library
- PyTorch
- TensorFlow
- Hugging Face Transformers

---

## License

This project is intended for educational and research purposes.

Please refer to the dataset and model licenses before using them in commercial applications.

---

## Author

**Durwang Deotale**

B.Tech – Computer Science & Engineering

Research Project – Automatic Speech Recognition (ASR) Model Benchmarking
