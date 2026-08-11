<div align="center">

<img src="https://img.shields.io/badge/PulseAI-AI%20Health%20Predictor-00D4AA?style=for-the-badge&logo=data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjQiIGhlaWdodD0iMjQiIHZpZXdCb3g9IjAgMCAyNCAyNCIgZmlsbD0ibm9uZSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj48cG9seWxpbmUgcG9pbnRzPSIyLDEyIDUsMTIgNyw2IDksMTggMTEsMTAgMTMsMTQgMTUsMTIgMjIsMTIiIHN0cm9rZT0iI2ZmZiIgc3Ryb2tlLXdpZHRoPSIyLjQiIHN0cm9rZS1saW5lY2FwPSJyb3VuZCIgc3Ryb2tlLWxpbmVqb2luPSJyb3VuZCIvPjwvc3ZnPg==" alt="PulseAI"/>

# PulseAI 🩺

### AI-Powered Medical Symptom Prediction System

[![Python](https://img.shields.io/badge/Python-3.9+-3776AB?style=flat-square&logo=python&logoColor=white)](https://python.org)
[![Flask](https://img.shields.io/badge/Flask-2.x-000000?style=flat-square&logo=flask&logoColor=white)](https://flask.palletsprojects.com)
[![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-SVC-F7931E?style=flat-square&logo=scikit-learn&logoColor=white)](https://scikit-learn.org)
[![Accuracy](https://img.shields.io/badge/Model%20Accuracy-98%25-00D4AA?style=flat-square)](https://github.com/ankit3347/PulseAI)
[![License](https://img.shields.io/badge/License-MIT-A855F7?style=flat-square)](LICENSE)
[![Status](https://img.shields.io/badge/Status-Active-00D4AA?style=flat-square)](https://github.com/ankit3347/PulseAI)

<p align="center">
  <b>Enter your symptoms → Get AI-powered disease prediction + full health report</b>
</p>

[Features](#-features) · [Demo](#-demo) · [Tech Stack](#-tech-stack) · [Installation](#-installation) · [How It Works](#-how-it-works) · [Dataset](#-dataset) · [Contact](#-contact)

---

</div>

## 📌 Overview

**PulseAI** is a full-stack web application that uses a trained **Support Vector Classifier (SVC)** machine learning model to predict diseases based on user-reported symptoms. Beyond prediction, it delivers a complete health report including descriptions, precautions, medications, diet plans, and workout guidance.

> ⚠️ **Disclaimer:** PulseAI is built for educational purposes. It is **not** a substitute for professional medical advice. Always consult a qualified healthcare professional.

---

## ✨ Features

| Feature | Description |
|---|---|
| 🤖 **AI Disease Prediction** | SVC model predicts from 41 diseases across 132 symptoms |
| 📋 **Full Health Report** | Disease description, precautions, medications, diet & workout |
| 🧠 **Psychology Test** | Timed 10-minute MCQ test with live countdown & instant scoring |
| 💊 **Medication Guide** | Evidence-based drug suggestions matched to predicted condition |
| 🥗 **Diet & Workout Plans** | Condition-specific dietary and exercise recommendations |
| 🎨 **Dark Theme UI** | Custom-built glassmorphism dark UI — no Bootstrap, no Tailwind |
| 📡 **Animated ECG Hero** | Live SVG ECG animation with traveling pulse dot on landing page |
| 🔔 **Toast Notifications** | Modern slide-in alerts replacing old modal dialogs |
| 📱 **Fully Responsive** | Mobile-first design with hamburger navigation |
| 👥 **User Tracking** | Psychology test users stored and displayed on Users page |

---

## 🎬 Demo

```
Symptoms Input  →  AI Prediction  →  Full Health Report
    fever              Allergy          ✓ Description
    cough                               ✓ Precautions
    skin_rash                           ✓ Medications
                                        ✓ Diet Plan
                                        ✓ Workout Guide
```

> Screenshots coming soon — run locally to see the full dark UI experience.

---

## 🛠 Tech Stack

### Machine Learning
```
Scikit-learn     →  Support Vector Classifier (SVC, RBF kernel)
Pandas           →  Dataset loading, preprocessing, CSV lookups
NumPy            →  Feature vector construction (binary symptom encoding)
Pickle           →  Model serialization / deserialization
```

### Backend
```
Python 3.9+      →  Core language
Flask            →  Web framework, routing, template serving
Jinja2           →  HTML templating with Python variables
```

### Frontend
```
HTML5            →  Semantic markup
CSS3             →  Custom dark design system (CSS variables, Grid, Flexbox)
JavaScript       →  Chip selector, counter animation, timer, toasts
SVG              →  ECG animation with animateMotion
```

### Data
```
Training.csv          →  4,920 cases × 132 symptoms + disease label
description.csv       →  41 disease descriptions
precautions_df.csv    →  Up to 4 precautions per disease
medications.csv       →  Medication recommendations per disease
diets.csv             →  Diet recommendations per disease
workout_df.csv        →  Workout recommendations per disease
Symptom-severity.csv  →  Severity weight (1–7) per symptom
```

---

## 📊 Model Performance

| Metric | Value |
|---|---|
| **Algorithm** | Support Vector Classifier (SVC) |
| **Kernel** | RBF (Radial Basis Function) |
| **Test Accuracy** | ~98% |
| **Diseases Covered** | 41 |
| **Symptom Inputs** | 132 |
| **Train / Test Split** | 80% / 20% |
| **Training Samples** | 3,936 |
| **Test Samples** | 984 |

### Why SVC over other models?

| Model | Test Accuracy | Chosen? |
|---|---|---|
| Decision Tree | 93.2% | ❌ Overfits easily |
| Random Forest | 97.1% | ❌ Slightly lower |
| **SVC (RBF)** | **98.0%** | **✅ Best accuracy + generalization** |

---

## 📂 Project Structure

```
PulseAI/
│
├── app.py                        # Main Flask application
├── svc.pkl                       # Trained SVC model (Pickle)
├── requirements.txt              # Python dependencies
│
├── datasets/
│   ├── Training.csv              # ML training data (4920 × 133)
│   ├── description.csv           # Disease descriptions
│   ├── precautions_df.csv        # Precaution recommendations
│   ├── medications.csv           # Medication recommendations
│   ├── diets.csv                 # Diet recommendations
│   ├── workout_df.csv            # Workout recommendations
│   └── Symptom-severity.csv      # Symptom severity weights
│
├── templates/
│   ├── landing.html              # Home page
│   ├── predict.html              # Symptom input + results
│   ├── about.html                # About page
│   ├── ptest.html                # Psychology test
│   └── users.html                # Users listing
│
└── static/
    ├── SCSS/
    │   ├── style.css             # Compiled dark theme CSS
    │   └── style.scss            # SCSS source
    └── [images]                  # Medical imagery assets
```

---

## ⚙️ Installation

### Prerequisites
- Python 3.9 or higher
- pip package manager
- Git

### Step 1 — Clone the repository
```bash
git clone https://github.com/ankit3347/PulseAI.git
cd PulseAI
```

### Step 2 — Create virtual environment
```bash
# Create
python -m venv venv

# Activate — Windows
venv\Scripts\activate

# Activate — Mac/Linux
source venv/bin/activate
```

### Step 3 — Install dependencies
```bash
pip install -r requirements.txt
```

### Step 4 — Run the application
```bash
python app.py
```

### Step 5 — Open in browser
```
http://localhost:5000
```

---

## 📦 Requirements

```txt
Flask>=2.3.0
scikit-learn>=1.3.0
pandas>=2.0.0
numpy>=1.24.0
```

Generate your own `requirements.txt` with:
```bash
pip freeze > requirements.txt
```

---

## 🔬 How It Works

### ML Pipeline

```
Training.csv
    │
    ├── Features (X)   →  132 binary symptom columns
    └── Target  (y)    →  prognosis (disease name)
            │
            ▼
    LabelEncoder  →  Convert disease strings to integers (0–40)
            │
            ▼
    train_test_split  →  80% train / 20% test
            │
            ▼
    SVC(kernel='rbf')  →  fit(X_train, y_train)
            │
            ▼
    Evaluate  →  accuracy_score ~98%
            │
            ▼
    pickle.dump(model)  →  svc.pkl
```

### Prediction at Runtime

```
User selects symptoms
        │
        ▼
JavaScript builds comma-separated string
"fever,cough,skin_rash"
        │
        ▼
Flask receives POST request
        │
        ▼
Build feature vector:
np.zeros(132)  →  set positions of selected symptoms to 1
        │
        ▼
model.predict([feature_vector])
        │
        ▼
Decode integer → disease name via LabelEncoder
        │
        ▼
Lookup: description, precautions, medications, diet, workout
        │
        ▼
Render results in predict.html
```

---

## 📊 Dataset

**Source:** [Medicine Recommendation System Dataset](https://www.kaggle.com/datasets/noorsaeed/medicine-recommendation-system-dataset) — Kaggle (Noor Saeed)

| File | Rows | Columns | Description |
|---|---|---|---|
| `Training.csv` | 4,920 | 133 | Symptom features + disease label |
| `Symptom-severity.csv` | 133 | 2 | Symptom + severity weight (1–7) |
| `description.csv` | 41 | 2 | Disease + clinical description |
| `precautions_df.csv` | 41 | 5 | Disease + 4 precautions |
| `medications.csv` | 41+ | 2 | Disease + medication |
| `diets.csv` | 41+ | 2 | Disease + dietary advice |
| `workout_df.csv` | 41+ | 2 | Disease + workout recommendation |

---

## 🗺 Roadmap

- [x] Core ML prediction pipeline
- [x] Flask web application
- [x] Full health report (description, precautions, medications, diet, workout)
- [x] Psychology test module
- [x] Dark theme UI with animations
- [x] Responsive mobile layout
- [ ] User authentication & health history
- [ ] Confidence scores (predict_proba)
- [ ] REST API endpoint for mobile apps
- [ ] PostgreSQL database (replace CSV lookups)
- [ ] Docker containerization
- [ ] Symptom image analysis (CV integration)

---

## 🤝 Contributing

Contributions are welcome! Here's how:

```bash
# 1. Fork the repo

# 2. Create your branch
git checkout -b feature/YourFeature

# 3. Commit your changes
git commit -m "Add: YourFeature description"

# 4. Push to your branch
git push origin feature/YourFeature

# 5. Open a Pull Request
```

---

## 📄 License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.

---

## 📬 Contact

<div align="center">

**Ankit Prajapati**
*B.Tech CSE | Data Science & AI | Full-Stack Developer*

[![Email](https://img.shields.io/badge/Email-ankitprajapati893@gmail.com-EA4335?style=flat-square&logo=gmail&logoColor=white)](mailto:ankitprajapati893@gmail.com)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-ankitprajapati3347-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://linkedin.com/in/ankitprajapati3347)
[![GitHub](https://img.shields.io/badge/GitHub-ankit3347-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/ankit3347)

</div>

---

<div align="center">

Made with ❤️ by [Ankit Prajapati](https://github.com/ankit3347)

⭐ **Star this repo if you found it helpful!**
<!-- just testing somehing -->

</div>
