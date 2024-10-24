# Multimodal Emotion Recognition Using Speech and Text

## Project Overview
This project implements a multimodal emotion recognition system that combines speech and text inputs to classify emotions. The goal is to develop a robust system by integrating deep learning and traditional machine learning models for both speech and text, using a late fusion approach. Our system leverages different features from both modalities to enhance accuracy in emotion detection.

## Datasets
- **Speech Dataset**: [RAVDESS](https://zenodo.org/record/1188976) (Ryerson Audio-Visual Database of Emotional Speech and Song)
- **Text Dataset**: [ISEAR](https://www.unige.ch/cisa/research/materials-and-online-research/research-material/) (International Survey on Emotion Antecedents and Reactions)
- **Late Fusion Dataset**: Real data gathered from YouTube, combining both speech and text inputs for final classification.

## Speech Modality
For the speech-based emotion recognition, the following models, features, and preprocessing techniques are used:

### Models
- CNN (Convolutional Neural Network)
- LSTM (Long Short-Term Memory)
- Random Forest (RF)

### Features
- **Chroma**: Pitch class profiles extracted from the audio.
- **Mel-spectrogram**: Represents the short-term power spectrum of sound.
- **MFCC (Mel Frequency Cepstral Coefficients)**: Captures timbral features from the audio.

### Data Augmentation
- **Random Noise**: Introduces noise into the audio samples to increase variability.
- **Time-Shift**: Applies a time shift to audio to slightly move the waveforms.

### Preprocessing
- **Trimming Silence**: Audio files are trimmed to remove leading and trailing silences, ensuring that only the essential part of the speech signal is analyzed.

## Text Modality
For the text-based emotion recognition, we use the following models, features, and preprocessing steps:

### Models
- GPT-2
- BERT (Bidirectional Encoder Representations from Transformers)
- XGBoost

### Features for XGBoost
- **TF-IDF (Term Frequency-Inverse Document Frequency)**: Used to quantify the importance of words in the text corpus.

### Preprocessing
- **Removing Numbers**: Eliminate numbers that do not contribute to the emotion detection process.
- **Stemming**: Reduce words to their base or root form.
- **Removing Stop Words**: Filter out common words like "the", "and", etc., which are not significant for emotion detection.

## Late Fusion
In the final phase, we employ **late fusion** to combine predictions from both speech and text models. A total of **49 different combinations** are tested, where at least one model from each modality (speech and text) is used to make the final emotion prediction.

## Block Diagram
![Block Diagram](block_diagram%20.png)

---

## Installation and Usage
1. Clone this repository:
   ```bash
   git clone https://github.com/yourusername/multimodal-emotion-recognition.git
