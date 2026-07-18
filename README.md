# GPT From Scratch

A decoder-only Transformer language model built from scratch in **PyTorch**.

This project is my implementation of a GPT-style language model while learning how Transformers work. The model is trained character-by-character on a text corpus and can generate new text after training.

The implementation includes:

- Character-level tokenization
- Token and positional embeddings
- Multi-Head Self-Attention
- Causal masking
- Feed-Forward Networks
- Residual connections
- Layer Normalization
- CUDA acceleration (if available)
- Automatic model saving after training

The architecture is heavily inspired by Andrej Karpathy's educational NanoGPT series and was written as a learning project.

---

## Features

- Decoder-only Transformer
- Character-level tokenizer
- Multi-head causal self-attention
- Positional embeddings
- Residual connections
- Dropout regularization
- AdamW optimizer
- Automatic GPU acceleration (CUDA)
- Saves trained weights as `language_model.pt`
- Autoregressive text generation
- Easily configurable hyperparameters

---

## Requirements

- Python 3.10+
- uv
- NVIDIA GPU (optional, but recommended)

If you don't already have **uv** installed:

```bash
pip install uv
```

---

## Running

Clone the repository:

```bash
git clone <repository-url>
cd gpt
```

Install all dependencies:

```bash
uv sync
```

Train the model:

```bash
uv run gpt.py
```

The script will:

1. Detect whether CUDA is available.
2. Train the Transformer.
3. Periodically print the training loss.
4. Save the trained model as `language_model.pt`.
5. Generate sample text.

---

## Dataset

By default the model trains on:

```
shakespeare.txt
```

To train on another dataset, simply replace the filename in `gpt.py` with another plain-text file.

Some examples include:

- Books
- Movie scripts
- Research papers
- Documentation
- Your own writing

A sample `feynman.txt` dataset is also included.

---

## Hyperparameters

Current defaults:

| Parameter | Value |
|-----------|------:|
| Batch Size | 32 |
| Context Length | 64 |
| Embedding Size | 384 |
| Attention Heads | 6 |
| Transformer Blocks | 6 |
| Learning Rate | 3e-4 |
| Max Iterations | 100000 |
| Dropout | 0.2 |

These can all be modified near the top of `gpt.py`.

---

## Output

After training completes, the project creates:

```
language_model.pt
```

This file contains the trained model weights and can be loaded later without retraining.

---

## Project Structure

```
gpt/
│
├── .venv/
├── gpt.py
├── shakespeare.txt
├── feynman.txt
├── pyproject.toml
├── uv.lock
├── README.md
└── LICENSE
```

---

## Future Improvements

Some features I'd like to add in future versions:

- Model checkpointing during training
- Resume training from saved checkpoints
- Validation loss evaluation
- GPU benchmarking
- Learning rate scheduler
- Temperature sampling
- Top-k and Top-p sampling
- Byte Pair Encoding (BPE) tokenizer
- Larger datasets
- Support for GPT-2 style architectures

---

## Credits

Created by **PAPEET2785**

Inspired by Andrej Karpathy's educational NanoGPT series.

Built using **PyTorch**.