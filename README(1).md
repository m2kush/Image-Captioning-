🖼️📜 Image Captioning Using CNN-LSTM | Flickr8k Dataset
This repository contains a complete image captioning pipeline implemented using Convolutional Neural Networks (CNN) for feature extraction and LSTM (Long Short-Term Memory) networks for text generation. The project demonstrates how to generate descriptive captions for images using deep learning.

✅ This is a Kaggle Notebook-based project built on the Flickr8k dataset.

🔍 Overview
The project uses a CNN + LSTM-based encoder-decoder architecture.

CNN (DenseNet201) extracts visual features from input images.

LSTM decodes these features to generate a natural language caption.

Combines techniques from Computer Vision and Natural Language Processing.


📦 Dataset Details
Dataset: Flickr8k Dataset

Contains 8,000 images with human-annotated captions per image.

Due to Kaggle's file size limits:

Only 5 sample test images have been uploaded.

The full captions dataset is uploaded to preserve training context.

Complete image dataset was used during local development/training.

🧠 Model Architecture
Encoder: Pretrained DenseNet201 (up to Global Average Pooling layer)

Decoder: LSTM layer with Embedding + Dense + Dropout

Image features and text sequences are merged and passed to the decoder

Added skip connection (residual addition of image embeddings post LSTM) to enhance performance

📈 Training
Data Generator class implemented to stream data batch-wise due to memory constraints.

Trained for 50 epochs using:

ModelCheckpoint (best model saving)

EarlyStopping (to prevent overfitting)

ReduceLROnPlateau (for learning rate scheduling)

Learning curve shows potential overfitting due to limited data

Validation performed on ~15% of dataset

🛠️ Utilities
Functions included for:

Text preprocessing

Tokenization

Feature extraction

Caption generation from image embeddings

Inference uses a greedy approach: predicts one word at a time until endseq

🔍 Sample Results
Captions generated show meaningful structure.

Some redundancy and bias (e.g., “blue shirt”) noted due to limited data and no attention mechanism.

Planned improvements:

Add attention layer to improve relevance

Use BLEU Score for quantitative evaluation

Train on larger dataset like Flickr30k or MS COCO

📌 Conclusion
This project presents a complete end-to-end solution for the image captioning problem using deep learning. While the current implementation is basic and limited by dataset size, it lays the groundwork for future improvements using advanced architectures and larger datasets.
