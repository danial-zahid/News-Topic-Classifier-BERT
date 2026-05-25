# News Topic Classifier Using BERT

🤖 A state-of-the-art NLP application that classifies news headlines into 4 categories using a fine-tuned BERT model.

## 📋 Overview

This project fine-tunes a pre-trained **BERT** model (`bert-base-uncased`) to classify news headlines into topic categories:
- 🌍 **World**
- ⚽ **Sports**
- 💼 **Business**
- 🔬 **Sci/Tech**

The model is trained on the **AG News dataset** with mixed precision (FP16) for faster training and inference.

## ✨ Features

- **Pre-trained BERT Model**: Leverages transformer architecture for better contextual understanding
- **Efficient Training**: Mixed precision (FP16) support with ~10-15 min training on T4 GPU
- **Web Interface**: Interactive Streamlit app for real-time headline classification
- **High Accuracy**: Achieves competitive performance on test set
- **Production Ready**: Includes evaluation metrics and saved models

## 🚀 Quick Start

### Prerequisites
- Python 3.8+
- GPU recommended (CUDA compatible)
- 4GB+ RAM

### Installation

```bash
# Clone the repository
git clone https://github.com/danial-zahid/News-Topic-Classifier-BERT.git
cd News-Topic-Classifier-BERT

# Install dependencies
pip install -r requirements.txt
```

## 📖 Usage

### 1. Train the Model

```bash
python train.py
```

This script will:
1. Download and load the AG News dataset
2. Tokenize headlines using BERT tokenizer
3. Fine-tune `bert-base-uncased` for 3 epochs
4. Save trained model and tokenizer to `saved_models/`

**Training time**: ~10-15 minutes on T4 GPU, ~45-60 minutes on CPU

### 2. Evaluate the Model

```bash
python evaluate.py
```

Displays:
- Overall accuracy on test set
- Weighted F1-score
- Per-class precision and recall

### 3. Use the Web Interface

```bash
streamlit run app.py
```

Opens an interactive web app at `http://localhost:8501` where you can:
- Enter any news headline
- Get instant topic predictions with confidence scores
- Test multiple headlines

## 🏗️ Project Structure

```
News-Topic-Classifier-BERT/
├── preprocess.py          # Data loading and tokenization
├── train.py               # Model fine-tuning pipeline
├── evaluate.py            # Evaluation on test set
├── app.py                 # Streamlit web application
├── requirements.txt       # Project dependencies
├── README.md              # This file
├── DEVELOPER_GUIDE.md     # Detailed code explanations
├── Task.md                # Project requirements
└── saved_models/          # Trained model and tokenizer
```

## 🐍 Running on Google Colab (Recommended)

No GPU? Train for free on Google Colab with T4:

1. Open [Google Colab](https://colab.research.google.com)
2. Upload this repository or clone from GitHub
3. Go to **Runtime → Change runtime type → Select T4 GPU**
4. Install dependencies:
   ```bash
   !pip install -r requirements.txt
   ```
5. Run training:
   ```bash
   !python train.py
   ```

## 📊 Model Details

- **Base Model**: `bert-base-uncased` (110M parameters)
- **Dataset**: AG News (120K training samples)
- **Epochs**: 3
- **Batch Size**: 16 (train), 32 (eval)
- **Optimizer**: AdamW
- **Learning Rate**: 2e-5
- **Mixed Precision**: FP16 enabled

## 📈 Performance

The trained model achieves:
- High accuracy on all 4 categories
- Balanced precision and recall
- Fast inference (~50ms per headline)

## 🛠️ Technologies Used

- **PyTorch**: Deep learning framework
- **Transformers**: Pre-trained BERT model
- **Streamlit**: Web application framework
- **Scikit-learn**: Evaluation metrics
- **Pandas & NumPy**: Data processing

## 📝 License

This project is open source and available under the MIT License.

## 👨‍💻 Author

**Danial Zahid**

## 🤝 Contributing

Contributions are welcome! Please feel free to submit pull requests or open issues for bugs and feature requests.

---

**For detailed code explanations**, refer to [DEVELOPER_GUIDE.md](DEVELOPER_GUIDE.md)
