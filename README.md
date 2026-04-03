# 🖼️ Image Captioning --- ResNet-101 + Transformer Decoder

An end-to-end deep learning project for generating natural language
captions from images using a CNN-Transformer architecture trained on the
MS COCO 2017 dataset.

## 🚀 Overview

This project implements an image captioning model combining: -
ResNet-101 as a visual feature extractor - Transformer Decoder for
sequence generation - Trained on MS COCO dataset (\~590K image-caption
pairs)

## 🧠 Architecture

### Visual Encoder

-   ResNet-101 (ImageNet pretrained)
-   Outputs 7×7 spatial features (49 tokens)
-   Feature projection: 2048 → 512

### Transformer Decoder

-   6 layers
-   Masked self-attention + cross-attention
-   Feed-forward network (Pre-LN)

### Output Layer

-   Linear (512 → vocab size \~10K)
-   Softmax activation

## ⚙️ Training Details

-   Loss: Cross-Entropy with label smoothing (0.1)
-   Teacher Forcing used
-   Optimizer: AdamW
-   LR Scheduler: Cosine annealing
-   Mixed Precision Training (AMP)

## 📂 Dataset

-   MS COCO 2017
-   \~118K images
-   5 captions per image (\~590K pairs)

## 🛠️ Tech Stack

-   Python
-   PyTorch
-   Torchvision
-   NumPy, Pandas
-   Matplotlib

## ▶️ How to Run

``` bash
git clone https://github.com/your-username/image-captioning.git
cd image-captioning

python -m venv venv
source venv/bin/activate  # Linux/macOS
venv\Scripts\activate     # Windows

pip install -r requirements.txt

python train.py
python inference.py --image path_to_image
```

## 📈 Features

-   CNN + Transformer architecture
-   Custom tokenizer
-   Checkpoint saving
-   GPU training support

## 📌 Future Improvements

-   Beam search decoding
-   Vision Transformer (ViT)
-   Web deployment

## 📜 License

MIT License
