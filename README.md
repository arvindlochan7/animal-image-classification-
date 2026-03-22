# 🐾 Animal Image Classification using CNN

A Convolutional Neural Network (CNN) built with TensorFlow/Keras to classify images across **10 animal categories** using the [Animals-10 dataset](https://www.kaggle.com/datasets/alessiocorrado99/animals10) from Kaggle.

---

Project Structure

```
animal-image-classification/
│
├── model.py              # Main training script
├── requirements.txt      # Python dependencies
├── .gitignore            # Git ignore rules
└── README.md             # Project documentation
```

---

Tech Stack

Tool and Purpose 

TensorFlow / Keras - CNN model building & training 
KaggleHub - Dataset download 
NumPy - Array operations 
Matplotlib & Seaborn - Visualization 
Scikit-learn - Confusion matrix 

---

 Model Architecture

```
Input (128x128x3)
    → Conv2D(32) + MaxPool
    → Conv2D(64) + MaxPool
    → Conv2D(128) + MaxPool
    → Flatten
    → Dense(128) + Dropout(0.5)
    → Dense(10, softmax)
```

- Optimizer: Adam (lr=0.001)  
- Loss: Categorical Crossentropy  
- Epochs: 50  
- Batch Size: 32  

---

 Instructions on usage:

 1. Clone the repo
```
git clone https://github.com/your-username/animal-image-classification.git
cd animal-image-classification
```

 2. Install dependencies
```
pip install -r requirements.txt
```

 3. Set up Kaggle API
- Download your `kaggle.json` from [Kaggle Account Settings](https://www.kaggle.com/settings)
- Place it at `~/.kaggle/kaggle.json`
- Or set environment variables:
  ```bash
  export KAGGLE_USERNAME=your_username
  export KAGGLE_KEY=your_api_key
  ```

 4. Run the model
```
python model.py
```

---

# Outputs

After training, the script generates:
- `training_history.png` — accuracy & loss curves
- `confusion_matrix.png` — model performance across classes
- `animal_classifier.h5` — saved model (excluded from git)

---

🐄 Dataset

Animals-10 contains ~26,000 images across 10 classes:
`dog, cat, horse, spider, butterfly, chicken, sheep, cow, squirrel, elephant`

Auto-downloaded via `kagglehub` — no manual setup needed.

---

 Notes

- Model files (`.h5`) are excluded via `.gitignore` due to size — use [Git LFS](https://git-lfs.github.com/) if you need to version them
- Training on CPU will be slow; a GPU or Google Colab is recommended for 50 epochs

---
