# Zero-Shot-Image-Classification-using-CLIP

In this notebook, we will learn about Zero-Shot Image Classification using a Vision Language Model (VLM) called CLIP. It was created as part of the Vision Language Models (VLMs) Bootcamp conducted by OpenCV University.

## 📌 Overview

Zero Shot refers to the fact that we will not need any training data to build the classifier.

**CLIP** (Contrastive Language-Image Pre-training) is a multimodal model developed by OpenAI that learns to associate images with their textual descriptions, enabling tasks like zero-shot classification and image retrieval.

## 🎯 Goals

In this notebook, we use CLIP to:

1. Load a pretrained CLIP model and processor.
2. Perform preprocessing on both text labels and images.
3. Classify images into candidate categories using zero-shot learning.
4. Explore how CLIP aligns visual and textual representations.

## 🛠 Model Used
We use the CLIP Vision Transformer variant `openai/clip-vit-base-patch32` from HuggingFace

## 🔍 How It Works
1. Model Loading: Load the pretrained CLIP model (CLIPModel) and processor (CLIPProcessor).
2. Preprocessing: Image- Resized, center-cropped, normalized, and converted to tensors.
                  Text- Tokenized into subwords, padded, and converted into tensors.
3. Embedding Generation: The CLIP model encodes both the image and candidate class labels into a shared embedding space.
4. Similarity Measurement: Cosine similarity is computed between the image embedding and the embeddings of candidate class labels.
5. The label with the highest similarity score is predicted as the image’s class.
