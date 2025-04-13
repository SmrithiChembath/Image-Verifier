### 📌 Project Title
**Deepfake Duel: Truth vs. Trickery**

---

### 🧠 Abstract / Overview
- ML-powered web app to detect deepfakes and classify images into **humans**, **vehicles**, or **animals**.
- Uses a fine-tuned **XceptionNet** model.
- Hosted publicly at: [thatlooksus.tech](https://www.thatlooksus.tech)

---

### 🗂 Dataset
- Based on a subset of the **ArtiFact_240K** dataset.
- Labels: `real (1)` or `fake (0)` + domain (`animal`, `vehicle`, `human`).
- Applied transforms: resizing, normalization, random flip/rotation for augmentation.

---

### 🧱 Model Architecture
- **XceptionNet** pretrained on ImageNet.
- Modified output layers:
  - Binary classifier (real vs. fake).
  - Multiclass classifier (domain).
- Loss: Binary Cross-Entropy + Cross-Entropy (weighted).
- Optimizer: **Adam**, with early stopping on validation loss.

---

### 💻 Web Application
- Built with **Flask**.
- Users upload images → app returns:
  - Prediction (Fake/Real)
  - Category (Human/Animal/Vehicle)
- Model loaded at server startup, inference using PyTorch.

---

### 🚀 Deployment
- Hosted on **Render**.
- Backend served via **gunicorn**.
- Setup:
  - `requirements.txt`
  - `Procfile`: `web: gunicorn app:app`
- Connected to a custom domain: **thatlooksus.tech**

---

### ⚠️ Challenges Faced
- **Git issues** with untracked files (`requirements.txt`, `Procfile`) → resolved with manual re-staging.
- **Render errors** due to Procfile and file/module name mismatches.
- Limited uptime due to **free hosting tier**.
- Large dataset caused **processing delays**.

---

### 📊 Results
- Validation accuracy: ~70%.
- Strongest performance in **human face detection**.
- Evaluation results stored in `test.csv`.

---

### 🧾 Conclusion
- End-to-end project showing practical use of ML for media verification.
- Combines CV, web dev, and deployment skills.
- Scalable for further research or commercial use.

---

### 🔗 Live Demo
[🌐 Visit the App](https://www.thatlooksus.tech)
