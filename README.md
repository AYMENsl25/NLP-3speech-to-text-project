you can check here the drive 
https://drive.google.com/drive/folders/1nEpbSnmZAFsIvIz9FZ4z023Kdslxt6jb?usp=sharing
# 📘 COE025 – Natural Language Processing  
## Project 3: Automatic Speech Recognition (ASR) for Spanish

---



## 📌 Project Description
This project is part of the **COE025: Natural Language Processing (Fall 2025–2026)** course.  
The objective of this project is to **analyze and compare different Automatic Speech Recognition (ASR) models** for **Spanish speech transcription**.

Spanish was chosen because it is one of the most widely spoken languages worldwide and has **complex phonetics**, which makes ASR a challenging task.

---

## 🌍 Why Spanish?
- Spoken by more than **500 million speakers worldwide**
- Rich phonetic diversity and accents
- Availability of strong open-source datasets and pretrained models
- Similar-sounding words increase transcription difficulty

The evaluated audio samples had a duration of approximately **12–15 seconds**.

---

## 🎧 Data & Sample
- One main evaluation sample was selected from **10 recorded samples**
- The project compares transcription quality and errors across models
- Errors were analyzed manually to better understand model behavior

---

## 🧹 Feature Extraction
Before feeding audio data into ASR models, several features were extracted:

- **Waveform (time domain):** Provides a general signal overview  
- **Spectrogram (frequency domain):** Shows energy distribution across frequencies  
- **Log-Mel Spectrograms:** Common representation for neural ASR  
- **MFCCs:** Classic compact features for speech processing  

These steps convert raw audio into structured features usable by neural models.

---

## 🔍 Models Implemented
Six different ASR models were implemented to cover both **CTC-based** and **Seq2Seq** approaches:

1. **CNN + CTC (Baseline)**
2. **Wav2Vec2-CTC (XLSR-53 Spanish)**
3. **HuBERT (CTC)**
4. **Whisper (Seq2Seq)**
5. **Parakeet (Seq2Seq)**
6. **SeamlessM4T (Seq2Seq)**

---

## 📈 Evaluation Metric
- **Word Error Rate (WER)**  
WER measures the percentage of incorrect words in a transcription.  
Lower WER indicates better performance.

---

## 📊 Model Results and Analysis

### 📌 CNN + CTC Baseline
- Average WER: **~19.5%**
- Common errors:
  - Misspellings
  - Missing words
  - Incorrect word segmentation
- Suggested improvements:
  - Add a language model for decoding
  - Fine-tune on domain-specific Spanish data

---

### 📌 Wav2Vec2-CTC (XLSR-53 Spanish)
- Average WER: **~27.8%**
- Main issue: word concatenation and missing punctuation
- Improvements:
  - Language model for beam search decoding
  - Post-processing and punctuation restoration

---

### 📌 HuBERT (CTC)
- Average WER: **~57%**
- Struggles with masked or noisy audio
- Frequent missing and incorrect words
- Improvements:
  - Fine-tuning on noisy data
  - Language model integration
  - Data augmentation

---

### 📌 Whisper (Seq2Seq)
- Average WER: **~10.9%**
- Strong punctuation and sentence structure
- Minor semantic errors observed
- Improvements:
  - Fine-tune on Spanish-specific data
  - Use larger Whisper models

---

### 📌 Parakeet (Seq2Seq)
- Average WER: **~29%**
- Main issues:
  - Domain mismatch
  - Accent and pronunciation variation
- Could be improved through fine-tuning

---

### ✅ Best Model: **SeamlessM4T (Seq2Seq)**
- Average WER: **~7.86%**
- Best overall performance
- Strong language modeling and contextual understanding
- Minor errors can be reduced with fine-tuning

---

## 🧠 Final Conclusion
Seq2Seq models significantly outperform CTC-based models in terms of **accuracy, punctuation, and context handling**.  
Among all tested models, **SeamlessM4T achieved the lowest WER**, making it the most effective ASR model for Spanish in this project.

CTC-based models remain useful for **real-time applications**, while Seq2Seq models are better for **high-quality transcription**.

---

## ✅ Recommendations
- **Real-time ASR:** Wav2Vec2, HuBERT  
- **High accuracy & punctuation:** Whisper, SeamlessM4T  
- **Multilingual ASR:** SeamlessM4T  
- **Spanish-only tasks:** Wav2Vec2 XLSR Spanish  

---

## 🛠 Tools & Technologies
- Python  
- PyTorch  
- HuggingFace Transformers  
- torchaudio  
- ASR evaluation tools  

---


