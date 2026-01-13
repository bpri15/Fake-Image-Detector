
# 🕵️‍♂️ Fake Image Detector

An end-to-end pipeline to detect AI-generated images (Deepfakes, GAN-based, DALL·E, etc.) using custom preprocessing and a CNN-based classifier.

> **Reference Paper:** [Detection of AI-generated Images (arXiv)](https://arxiv.org/abs/2311.12397)  
> **Blog:** [Project Walkthrough on Medium](https://medium.com/p/fc2024e3e716)

---

## 📂 Datasets Used

- [🎨 ArtiFact: Real and Fake Image Dataset](https://www.kaggle.com/datasets/ravidussilva/real-ai-art)
- [🧠 DALL·E Recognition Dataset](https://www.kaggle.com/datasets/superpotato9/dalle-recognition-dataset/data)

> ⚠️ Note: Only a subset of each dataset was used for training to maintain diversity and balance.

---

## 🛠️ Features & Architecture

- Custom preprocessing (see `preprocessing/` folder).
- CNN-based binary image classifier (`classifier.h5`).
- Investigations into:
  - **Pixel fluctuation ratios** (see `sandbox/pixel_fluctuation.ipynb`)
  - Noise pattern detection
  - Rotation artifacts

---

## 🚀 How to Run the Project

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/fake-image-detector.git
cd fake-image-detector
```

### 2. Install Dependencies

Create a virtual environment (optional but recommended):

```bash
python3 -m venv venv
source venv/bin/activate  # or venv\Scripts\activate on Windows
```

Install required packages:

```bash
pip install -r requirements.txt
```

> If `requirements.txt` is missing, install the following common packages:
```bash
pip install numpy pandas matplotlib scikit-learn opencv-python tensorflow
```

### 3. Prepare Datasets

- Download the datasets from Kaggle (see links above).
- Place them in a folder structure like:
  ```
  datasets/
    artifact/
      real/
      fake/
    dalle/
      real/
      fake/
  ```

Update paths accordingly in `train.ipynb` and `testing.ipynb`.

### 4. Train the Model

Open and run `train.ipynb` in Jupyter or Colab:

```bash
jupyter notebook train.ipynb
```

- This will preprocess the data and train the CNN model.
- The trained model will be saved as `classifier.h5`.

### 5. Test the Model

Open and run `testing.ipynb` to test the model on unseen images.

---

## 🧪 Research Logs

**17/02/2024**
- Removed noise-adding filters.
- Introduced `pixel_fluctuation_ratio` as a feature.

**18/02/2024**
- Explored matrix rotation without noisy affine transformations.

---

## 📁 Project Structure

```
fake_image_detector/
├── checkpoints/             # Saved model checkpoints
├── preprocessing/           # Image preprocessing scripts
├── sandbox/                 # Experimental notebooks (e.g., pixel fluctuation)
├── classifier.h5            # Trained model
├── train.ipynb              # Training pipeline
├── testing.ipynb            # Inference pipeline
├── .gitignore
├── LICENSE
└── README.md
```

---


