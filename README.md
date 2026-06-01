# image-caption-generator
# Image Caption Generator — Multi-Model Comparison

Compares three vision-language models on deliberately hard images 
to show how model architecture affects caption quality.

## Models Used
- **BLIP base** (Salesforce) — describes what pixels look like
- **GIT base** (Microsoft) — describes what things are called  
- **BLIP-2** (Salesforce) — understands what things mean

## Key Finding
Running all three on the same 6 hard images revealed a clear 
progression from pixel-level description to semantic reasoning.

| Image | BLIP base | GIT base | BLIP-2 |
|---|---|---|---|
| Eye closeup | "a close up of a blue eye" | "the pupil of the eye is black" | "a close up of a person's eye with a blue iris" |
| Foggy forest | "a forest filled with tall trees" | "pine trees in the fog......." | "a dark foggy forest with tall trees" |
| Food art | "a plate with a sandwich and a crown" | "lettuce and tomato on a plate" | "a plate with a sandwich made to look like a princess" |
| Leaf insect | "a green leaf with red spots" | "i found this plant near my house" | "a group of green and red bugs on a leaf" |
| Optical illusion | "black and white spiral pattern" | "abstract vector background" | "a black and white optical illusion image of a spiral" |
| Underwater | "large group of fish" | "people snorkelling in the sea" | "two people swimming with sun shining through the water" |

## Notable Failures
- All 3 models missed the leaf insect — camouflage fools vision 
  models exactly like it fools humans
- GIT stalled on the foggy forest (trailing dots)
- None identified the food as a face until BLIP-2 caught "princess"

## Run It Yourself
Open in Colab → Runtime → T4 GPU → Run all cells

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1dRV0ukfmL0rpb46hCpyvhCTLeFiQ390B?usp=sharing)

## Setup
```bash
pip install -r requirements.txt
```

## Tech Stack
Python · HuggingFace Transformers · PyTorch · Gradio · BLIP · BLIP-2 · GIT
