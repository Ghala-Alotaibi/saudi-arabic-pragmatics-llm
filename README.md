# Evaluating Pragmatic Understanding of Saudi Arabic in LLMs
CS421 Selected Topics in Computer Science — King Faisal University
Group 4, Section 63 · Instructor: Dr. Hala Hamdoun

**Team:** Ghala Alotaibi (223047156), Salha Almarri (223042287), Haya Almuslim (223034961)

## What this is
A Comparative Study evaluating how well four LLMs understand intended meaning in Saudi Arabic. One identical zero-shot pipeline (same Arabic prompt, temperature 0 greedy decoding, same digit-extraction) is applied to:

- **ALLaM-7B-Instruct-preview** (Saudi-aligned baseline)
- **Jais-13B**
- **LLaMA-3-8B-Instruct**
- **Qwen2.5-7B-Instruct**

Evaluation:
- **Pragmatics:** 18 Saudi-dialect MCQs — 6 sarcasm, 6 indirect speech acts, 6 idioms/proverbs (chance 25%)
- **Emotion:** ArPanEmo 11-way emotion classification, 176 posts (chance ≈9%)

## Results
| Model | Pragmatics | Emotion |
|---|---|---|
| ALLaM-7B (baseline) | **88.9%** | **54.0%** |
| Qwen2.5-7B | 83.3% | 43.2% |
| Jais-13B | 61.1% | 22.7% |
| LLaMA-3-8B | 44.4% | 31.2% |

Full tables and per-item errors in `results/`.

## How to reproduce
1. Open `CS421_Experiment_Group4.ipynb` in Google Colab.
2. Runtime > Change runtime type > A100 GPU.
3. Upload `ArPanEmo_test.csv` (Althobaiti 2023) to `/content/`.
4. Run all cells. Fixed seeds (`SEED=42`) reproduce exact numbers.

Gated model access required: LLaMA-3 and Jais on Hugging Face.
