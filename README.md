# Task 2: Long Hair Identification and Gender Correction

## 📌 Objective
The goal of this task is to build a system that can **identify long hair** in facial images and use it to make a more realistic **gender classification** for individuals aged between 20 to 30.

### 🎯 Special Rules:
- **If person is aged between 20 and 30**:
  - Predict as **Female** if hair is long, even if facial features say Male.
  - Predict as **Male** if hair is short, even if facial features say Female.
- **If person is NOT between 20 and 30**:
  - Predict actual gender based on features only (no hair length influence).

---

## 🧠 Model Overview

We used a custom **CNN-based model** trained on the UTKFace dataset. Additional logic was added for:
- **Hair Length Classification** (via image segmentation or preprocessing).
- Age filtering to apply special rules for ages 20–30.

---

## 🗃️ Folder Structure
---

## 📋 Dataset Used
- **UTKFace Dataset**: Used for gender and age classification.
- **Custom Annotations** for hair length based on visual inspection or manual labeling.

---

## 🔄 Working Pipeline

1. **Load model**
2. **Detect age and gender**
3. **Check hair length** using image region or a threshold method
4. **Apply correction rules**:
   - If age in 20-30 and long hair → predict Female
   - If age in 20-30 and short hair → predict Male
   - Else → use model gender output

---

## ▶️ How to Run

1. **Install dependencies**
   ```bash
   pip install -r requirements.txt
