# Image_clef_2025
VIGCAP — Medical Image Caption Generation using Vision-Language Models
Overview

VIGCAP is a vision-language model designed for automatic medical image captioning. The system takes a biomedical image as input and generates a natural language caption describing the image content.

The architecture combines:

ViT-Base/16 as the image encoder
GPT-2 as the language decoder
Linear projection bridge for visual-text alignment
Prefix-based conditioning mechanism

This project was developed for the ImageCLEFmed 2026 Caption Prediction challenge.

Architecture

Input Medical Image ↓ Preprocessing (Resize + Normalize) ↓ ViT-Base/16 Encoder ↓ Linear Projection + LayerNorm ↓ Prefix Injection ↓ GPT-2 Decoder ↓ Generated Medical Caption

Training Strategy
Phase 1
Freeze ViT encoder
Train projection layer + GPT-2 decoder
Learning Rate: 5e-4
Epochs: 3
Phase 2
Fine-tune entire model end-to-end
Learning Rate: 1e-5
Epochs: 5
Dataset
Dataset: ImageCLEFmed 2026 Caption Prediction
Source: PubMed Central Open Access
Size: 200K+ biomedical images

The dataset contains:

Radiology images
Histology figures
Microscopy images
Biomedical illustrations
Evaluation Metrics

The model is evaluated using:

BERTScore (Primary Metric)
ROUGE
BLEURT
Semantic Similarity
MedCAT
Alignment Score
Results
Metric	Score
BERTScore	0.6033
ROUGE	0.3889
Similarity	0.7406
BLEURT	0.3473
MedCAT	0.3412
Alignment	0.1633
Overall Score	0.3861
Technologies Used
Python
PyTorch
Hugging Face Transformers
Vision Transformer (ViT)
GPT-2
Kaggle GPU (T4 ×2 / P100)
Future Improvements
Replace GPT-2 with BioGPT
Add BLIP-2/Q-Former style architecture
Use UMLS concept supervision
Train modality-specific models
Retrieval-augmented caption generation

<img width="1569" height="860" alt="image" src="https://github.com/user-attachments/assets/f03ba4d5-86f9-4f58-a146-bb44a587c743" />
<img width="1338" height="771" alt="image" src="https://github.com/user-attachments/assets/84284e89-9051-462e-8b0e-417e83ddd6f9" />


Author

Madhab Padhi BML Munjal University, India

Under the Guidance of Atul Mishra

Acknowledgements

This project was developed as part of the ImageCLEFmed 2026 Caption Prediction task using Kaggle GPU resources.
