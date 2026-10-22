# Emotion2Art
**Emotion classification → image generation** · Personal AI prototype

A pipeline that interprets a short English text about a feeling, predicts one of six emotion labels, and uses that result to condition an illustrated image prompt.

This project is **separate from Emora**, my multimodal EEG + eye-tracking graduation project.

## System overview

```text
User text
   |
   v
Fine-tuned DistilBERT
   |  sadness · joy · love · anger · fear · surprise
   v
Emotion-aware prompt
   |
   v
Stable Diffusion 1.5
   |
   v
Generated illustration + detected emotion (Gradio)
```

## Models and evaluation

| Component | Implementation |
| --- | --- |
| Emotion model | `distilbert-base-uncased`, fine-tuned on the [dair-ai/emotion](https://huggingface.co/datasets/dair-ai/emotion) dataset |
| Classes | 6 |
| Reported test accuracy | **94.15%**, as recorded in the project README |
| Image generation | `runwayml/stable-diffusion-v1-5` |
| Interface | Gradio |
| Trained weights | [Hugging Face model](https://huggingface.co/Heaikyoraku/emotion-model-byHasoosy) |

**Scope:** The metric concerns **text emotion classification**, not the quality of generated art or EEG-based emotion recognition. The artwork is prompt-driven rather than a separately fine-tuned diffusion model.

## Demo

![Emotion2Art application demo](https://github.com/user-attachments/assets/b0d42401-baa9-402c-b6ef-6f075eff2628)

## Repository contents

- [Notebook: Emotion2Art pipeline](./Emotion2Art_Pipeline_by_Hasoosy%20(1).ipynb) — preprocessing, model training/evaluation, inference, image generation, and Gradio.
- [Trained emotion classifier](https://huggingface.co/Heaikyoraku/emotion-model-byHasoosy) — hosted model artifacts.

## Reproducing the prototype

This was built as a notebook workflow. It currently includes local model-directory placeholders and assumes access to GPU resources for diffusion inference. **It is not yet reproducible with one command** from a clean clone. To run it, configure model paths, install notebook dependencies, and execute cells in order.

## Next steps

- Replace local paths with configurable model identifiers.
- Separate training and inference; pin dependencies.
- Add unit tests, example prompts, and an evaluation set for the generated outputs.
