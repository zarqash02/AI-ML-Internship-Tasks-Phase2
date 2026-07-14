# 📰 📰 Phase 2 - Task 1: News Topic Classification using BERT

A Natural Language Processing (NLP) project that fine-tunes a pre-trained **BERT** model to classify news articles into different topic categories using the Hugging Face Transformers library and PyTorch.

## 📌 Project Overview

This project demonstrates how to build a high-performance text classification model by fine-tuning BERT on a news dataset. The notebook covers the complete machine learning workflow, including:

* Loading and preprocessing the dataset
* Tokenizing text using BERT tokenizer
* Fine-tuning a pre-trained BERT model
* Training and validation
* Model evaluation
* Predicting topics for unseen news articles

---

## 🚀 Features

* Fine-tunes a pre-trained **BERT** model for multi-class text classification
* Uses the Hugging Face **Transformers** library
* Implements efficient text tokenization
* Trains using **PyTorch**
* Evaluates model performance using standard classification metrics
* Supports authenticated Hugging Face downloads using an access token for higher rate limits

---

## 🛠️ Technologies Used

* Python
* Jupyter Notebook
* PyTorch
* Hugging Face Transformers
* Hugging Face Datasets
* Hugging Face Hub
* Scikit-learn
* NumPy
* Pandas
* Matplotlib

---

## 📂 Repository Structure

```
.
├── News_Topic_Classifier_BERT_1_HFToken.ipynb
├── README.md
└── requirements.txt (optional)
```

---

## ⚙️ Installation

Clone the repository:

```bash
git clone https://github.com/your-username/news-topic-classification-bert.git
cd news-topic-classification-bert
```

Install the required packages:

```bash
pip install torch transformers datasets huggingface_hub scikit-learn pandas numpy matplotlib
```

---

## 🔑 Hugging Face Authentication

This notebook uses a Hugging Face Access Token to authenticate downloads.

You can either:

### Option 1: Set an environment variable (recommended)

**Windows PowerShell**

```powershell
$env:HF_TOKEN="your_huggingface_access_token"
```

**Windows Command Prompt**

```cmd
set HF_TOKEN=your_huggingface_access_token
```

### Option 2: Paste your token directly into the notebook

```python
HF_TOKEN = "your_huggingface_access_token"
```

Authentication removes anonymous download limits and enables faster access to Hugging Face models and datasets.

> **Do not commit your access token to GitHub.**

---

## 📊 Workflow

1. Import required libraries
2. Authenticate with Hugging Face
3. Load the news dataset
4. Preprocess and tokenize text
5. Load a pre-trained BERT model
6. Fine-tune the model
7. Evaluate performance
8. Make predictions on new samples

---

## 📈 Model

* **Model:** BERT (Bidirectional Encoder Representations from Transformers)
* **Framework:** Hugging Face Transformers
* **Task:** Multi-class News Topic Classification

---

## 📷 Example Prediction

**Input**

```
Apple unveils its latest AI-powered smartphone with improved battery life.
```

**Predicted Topic**

```
Technology
```

---

## 📚 Learning Outcomes

Through this project, I gained practical experience with:

* Transfer Learning
* Natural Language Processing (NLP)
* Transformer-based models
* BERT fine-tuning
* Text preprocessing
* Model evaluation
* Hugging Face ecosystem
* PyTorch training workflow

---

## 🤝 Contributing

Contributions, suggestions, and improvements are welcome. Feel free to fork the repository and submit a pull request.

---

## 📄 License

This project is intended for educational and learning purposes.
