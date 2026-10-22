# Emotion2Art

**From written emotion to generated artwork**

Emotion2Art is an end-to-end text-to-art AI pipeline. It classifies the emotion in a short English message and builds a matching prompt for a generative image model, with a Gradio interface for exploration.

## Pipeline

```text
Text input --> Fine-tuned DistilBERT --> 6-way emotion classification
                                            |
                                            v
                                    Emotion-conditioned prompt
                                            |
                                            v
                                      Stable Diffusion
                                            |
                                            v
                                  Artwork + predicted label
```

## Models & results

| | |
| :-- | :-- |
| Emotion classifier | `distilbert-base-uncased` fine-tuned on [dair-ai/emotion](https://huggingface.co/datasets/dair-ai/emotion) |
| Emotion classes | sadness · joy · love · anger · fear · surprise |
| Reported classifier test accuracy | **94.15%** |
| Image model | Stable Diffusion 1.5 |
| Interface | Gradio |
| Model weights | [Hugging Face](https://huggingface.co/Heaikyoraku/emotion-model-byHasoosy) |

The 94.15% figure measures **text classification**, not generative-image quality.

## Demo

![Emotion2Art interface](https://github.com/user-attachments/assets/b0d42401-baa9-402c-b6ef-6f075eff2628)

## Code

[Open the notebook](./Emotion2Art_Pipeline_by_Hasoosy%20(1).ipynb) to explore preprocessing, fine-tuning, evaluation, image generation, and the Gradio interface. The inference cells require GPU access for diffusion and configuration of the model directory paths.

<sub>Separate from **Emora**, my multimodal EEG + eye-tracking graduation project.</sub>
