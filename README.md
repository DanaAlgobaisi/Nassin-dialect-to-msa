# Nassin-dialect-to-msa
Real-time Arabic dialect-to-MSA translation using a fine-tuned AraT5 model, trained on 26,000+ Saudi/Gulf dialect–MSA sentence pairs.

# Nassin (نصّين): Bridging the Gap to Formal Arabic

Real-time Arabic dialect-to-MSA translation using a fine-tuned AraT5 model.
Built for **Arabthon** (Modern Standard and Classical Arabic Track).

📄 [View the project poster](Nassin.pdf)
![Training results](training_loss.jpg)

## Overview

Arabic speakers mostly communicate in dialects ("Ammiya"), while professional, legal, and educational writing requires Modern Standard Arabic (MSA / "Fusha"). Nassin is a fine-tuned AraT5 model that acts as a real-time "Formalizer": it corrects grammar and replaces colloquial expressions with proper terminology while preserving the original meaning.

## Use Cases

- **Corporate:** drafting formal emails, reports, and meeting minutes.
- **Customer Service:** converting slang complaints into structured formal text.
- **Education:** helping students move from colloquial to academic writing.
- **Government Services:** easier communication between citizens and official portals.

## Dataset

- Collected from the Composite Corpus (PADIC + NADI).
- Cleaned, sampled, and split into training and validation sets.
- Size: ~26,000 dialect/MSA sentence pairs.

## Methodology

1. **Data Ingestion & Collection:** curated dataset of 26,000 pairs (Saudi/Gulf dialect to MSA).
2. **Preprocessing & Tokenization:** text cleaning, noise removal, AraT5 tokenizer.
3. **Model Selection:** `UBC-NLP/AraT5-base` (encoder-decoder transformer).
4. **Fine-Tuning:** AdamW optimizer, learning rate 3e-4, 5 epochs, P100 GPU.
5. **Inference & Deployment:** Beam Search decoding for high-accuracy output.

## Training Results

| Epoch | Training Loss | Validation Loss |
|-------|---------------|-----------------|
| 1 | 0.510000 | 0.484640 |
| 2 | 0.424000 | 0.393032 |
| 3 | 0.365400 | 0.322750 |
| 4 | 0.348400 | 0.288922 |
| 5 | 0.302700 | 0.277236 |

- Solved "mode collapse" by using a 3e-4 learning rate.
- Correctly resolves Saudi dialect negation.
- Real-time translation on a P100 GPU.

## Tech Stack

Python, PyTorch, Hugging Face Transformers, T5 (AraT5).

## Future Work

- **Voice Integration (ASR):** speak in dialect, get formal text.
- **Browser Plugin:** Chrome extension for Gmail/Outlook.
- **Multi-Dialect Support:** Egyptian and Levantine dialects.

## Team

- Danah Alanazi
- Dana Algobaisi
- Nuwayir Alarifi
