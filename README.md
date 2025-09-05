# An AI Crop Doctor for Every Farmer's Pocket 🌱

 Feeding the world is a huge challenge, and crop diseases that wipe out harvests don't make it any easier. We have powerful AI that can spot these diseases from a single photo, but there's a catch: these AI models are massive, requiring powerful computers.

This project tackles that problem head-on. We've developed a method called **Context-Aware Adaptive Quantization (CAAQ)** to shrink a powerful AI model so it can run on the kind of smartphone a farmer might actually own.

This repository contains the code and research behind our work. We hope it can be a step towards making advanced agricultural technology accessible to everyone.

---
## 🧠 What's the Big Idea?

So, how do you fit a giant AI brain onto a regular phone? The answer is a process called **quantization**.

Think of it like compressing a beautiful, high-resolution photo into a smaller JPG to save space. You lose a little bit of imperceptible detail, but now the photo is small enough to email. Standard quantization techniques do this with AI models, but they often lose too much "detail," making the model less accurate.

Our method, **CAAQ**, is a smarter way to do this. By using **Quantization-Aware Training (QAT)**, we "teach" the model how to be small *during* its training process. It learns to focus on the most important details for diagnosing diseases, resulting in a model that is both tiny and highly effective.

---
## ✨ Why Should You Care? The Results

We didn't just make the model smaller; we made it better in almost every way that matters for real-world use.

* 📱 **It Fits on (Almost) Any Phone:** We crushed the model's size by **74%**, from a bulky 16.55MB down to just **4.24MB**. This is small enough for easy deployment on mobile devices.
* ⚡ **It's Fast:** The model gives an answer in about 28 milliseconds—a **2x speedup**. That's fast enough for real-time diagnosis right in the field.
* 🎯 **It's Actually *More* Accurate:** Here’s the surprising part. Our small, fast model was **1.59% more accurate** than the original, full-sized one! The training process acted as a regularizer, forcing the model to learn more robust features.

---
## 🛠️ Getting Started

To get a local copy of the code, clone the repository:
```bash
git clone [https://github.com/Shivamrajput4u/CAAQ-Crop-Disease-Diagnosis.git](https://github.com/Shivamrajput4u/CAAQ-Crop-Disease-Diagnosis.git)
cd CAAQ-Crop-Disease-Diagnosis
```

---
## 💾 Dataset

Our model was trained on a combination of two public datasets. You will need to download them and prepare them for the training script.

* **PlantDoc:** [Download from GitHub](https://github.com/pratikkayal/PlantDoc-Object-Detection-Dataset)
* **Plant Village:** [Download from Kaggle](https://www.kaggle.com/datasets/vipoooool/new-plant-diseases-dataset)

---
## ⚙️ How to Use It

Once you're set up, you can either train a new model from scratch or use our pre-trained model to diagnose a crop disease from an image.

**To train a new model:**
```bash
python train.py --data_path /path/to/your/dataset --epochs 15 --batch_size 32
```

**To diagnose an image:**
```bash
python inference.py --model_path models/caaq_quantized_int8.pth --image_path /path/to/your/image.jpg
```

---
## 📊 The Proof is in the Pudding

Here’s a quick look at the numbers. We compared our final, compact CAAQ model against the original, full-sized version.

| Model Type                | Accuracy (%) | Size (MB) | Speed (ms/image) |
|---------------------------|--------------|-----------|------------------|
| Original FP32 Model       | 42.46        | 16.55     | 57.28            |
| **Our CAAQ Model (INT8)** | **44.05** | **4.24** | **27.72** |

---
## 📄 Using Our Work

We're passionate about open science! If you use our code or ideas in your research, we'd be grateful if you'd cite our paper.
```bibtex
@misc{shivam2025caaq,
  author       = {Kumar Shivam},
  title        = {Context-Aware Adaptive Quantization for Multi-Crop Disease Diagnosis: An Extension of Similarity-Preserving Quantization},
  year         = {2025},
  publisher    = {GitHub},
  journal      = {GitHub repository},
  howpublished = {\url{https://github.com/Shivamrajput4u/CAAQ-Crop-Disease-Diagnosis}},
  url          = {https://github.com/Shivamrajput4u/CAAQ-Crop-Disease-Diagnosis}
}
```

---
## 📜 License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
