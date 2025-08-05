# 🎨Emotion2Art 
Let kids’ feelings turn into art using AI.
This project combines a fine-tuned emotion classification model with a generative image model to visually express children's emotions described through text. It aims to help kids express themselves emotionally in a fun and supportive way.

# 💡 How It Works
User Input: The user writes a sentence describing the child's emotional state.

Emotion Detection: A fine-tuned DistilBERT model classifies the emotion from the text.

Prompt Creation: A descriptive prompt is generated based on the emotion and the user's sentence.

Image Generation: The prompt is sent to the Stable Diffusion model to generate an expressive artwork.

Gradio Interface: Users interact through a clean Gradio interface to view and download the result.

<img width="2379" height="1580" alt="output (19)" src="https://github.com/user-attachments/assets/e5340857-2371-4bb9-9a91-d34e6e9e2b28" />



# 🧠 Models Used
Emotion Classifier: Fine-tuned DistilBERT model by me :)

Image Generator: runwayml/stable-diffusion-v1-5 (Hugging Face)

# 📊 Model Performance & Training Details
Model: DistilBERT fine-tuned for Emotion Classification
Base model: distilbert-base-uncased

Training dataset: Emotion classification dataset (custom/preprocessed)

Number of classes: 6 (sadness, joy, love, anger, fear, surprise)

Epochs: 3

Final Accuracy: 94.15% on test set 

Evaluation metric: Accuracy (using sklearn accuracy_score)


# 🛠️ Tech Stack
Python

Hugging Face Transformers

Hugging Face Diffusers

PyTorch

Gradio

# 📁 Project Structure
emotion-model-byHasoosy/ → contains the fine-tuned emotion classifier.

Emotion2Art_Pipeline_by_Hasoosy.ipynb → full integration pipeline with user interface.

output.png → sample generated art.
# examples:
<img width="512" height="512" alt="output (6)" src="https://github.com/user-attachments/assets/00662cfa-5e90-424b-a4ac-679287223175" />

<img width="512" height="512" alt="output (2)" src="https://github.com/user-attachments/assets/98c373a6-475a-4e42-82d6-7c6dcd52e121" />

<img width="512" height="512" alt="output (17)" src="https://github.com/user-attachments/assets/781052a0-cd24-4e8c-ab15-87b3c074ed45" />

<img width="512" height="512" alt="image (3)" src="https://github.com/user-attachments/assets/6739b596-642e-4c89-84e9-979fb343cd0d" />

<img width="512" height="512" alt="image (2)" src="https://github.com/user-attachments/assets/8345a243-b3e0-45a9-a510-3c7f74d6ed66" />

<img width="512" height="512" alt="output (9)" src="https://github.com/user-attachments/assets/dfdb67db-aa7f-42eb-b255-564decca7fb9" />

# demo:
<img width="2334" height="978" alt="image" src="https://github.com/user-attachments/assets/b0d42401-baa9-402c-b6ef-6f075eff2628" />
<img width="1130" height="926" alt="image" src="https://github.com/user-attachments/assets/07c70d14-ec7f-47f5-aa04-bee995530e7a" />


# 📝 Notes
The emotion classifier was fine-tuned on a dataset with six labels: sadness, joy, love, anger, fear, surprise.

# 🎨 Drawing Styles
The current version is locked to pastel colors to ensure a soft, childlike feel in the generated art.

Users can manually change the style prompt inside the code if needed.

# Example:
style_prompt = "A watercolor drawing in pastel tones"
Styles are not dynamically applied by the model itself, but rather influence the text prompt passed to Stable Diffusion.

# 🧠 Future plans:

Let users change drawing styles from the interface.

Explore training or fine-tuning models that better support artistic style control directly.

Future versions may include a custom-trained diffusion model.


