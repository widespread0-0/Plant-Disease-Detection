# 🌿 Plant Disease Detector  
**An end-to-end image classification system that diagnoses 38 plant diseases from a single leaf photo**  

![Demo](https://via.placeholder.com/800x400.png?text=Demo:+Upload+Leaf+→+Instant+Diagnosis)  

### 🚀 Live Demo  (NOT OUT YET)
[https://your-username-plant-disease-detector.hf.space](https://huggingface.co/spaces/your-username/plant-disease-detector) *(or your Streamlit/Gradio link)* 

### 🎯 Goal  
Take a phone photo of a plant leaf → instantly tell if it’s healthy or which disease it has (38 classes across 14 crop species, e.g., Tomato Late Blight, Apple Scab, Corn Rust).

### ✨ Features  
- Full data pipeline (ingestion → cleaning → augmentation → stratified split)  
- Classical ML baselines (HOG + color features → SVM / Random Forest / XGBoost) → 70–82 % accuracy  
- Deep learning models  
  - Small custom CNN from scratch → ~90 %  
  - Transfer learning (EfficientNet-B0 pretrained on ImageNet) → 97–99 % in just a few epochs  
- Soft-voting ensemble of 4–5 models → 99.4–99.6 % accuracy (state-of-the-art for this dataset)  
- One-click web app (Streamlit or Gradio) with real-time prediction in <1 second  
- Clear data-flow diagram and comparison tables in notebooks

### 📊 Dataset  
- Primary: [PlantVillage Dataset](https://www.kaggle.com/datasets/abdallahalidev/plantvillage-dataset) (~55 k images, 38 classes)  
- Alternative (faster training): [New Plant Diseases Dataset](https://www.kaggle.com/datasets/vipoooool/new-plant-diseases-dataset) (~20–30 k images)  
Images are cleanly organized by plant → disease/healthy.

### 📁 Project Structure  
```
├── data/                    # (dataset – add via Kaggle link or shared Drive)
├── notebooks/ (ALL NOTEBOOKS USED FOR EXPERIMENTATION)
│   ├── 01_data_pipeline.ipynb
│   ├── 02_eda.ipynb
│   ├── 03_classical_ml.ipynb
│   ├── 04_custom_cnn.ipynb
│   ├── 05_transfer_learning.ipynb
│   └── 06_evaluation_ensemble.ipynb
├── src/
│   ├── features.py          # HOG + color histogram extraction
│   ├── models.py            # All trained models (.pkl / .pth)
│   └── ensemble.py          # Soft-voting inference
├── app.py                   # Streamlit/Gradio app
├── requirements.txt
└── README.md
```

### ⚡ Quick Start  
```bash
# 1. Clone & install
git clone https://github.com/your-team/plant-disease-detector.git
cd plant-disease-detector
pip install -r requirements.txt

# 2. Download dataset (once) and put in data/raw or use Kaggle API
# kaggle datasets download -d abdallahalidev/plantvillage-dataset

# 3. Run the web app
streamlit run app.py
# or
gradio app.py
```

### 📈 Results Summary  (WHAT WE SHOULD TRY TO ACHIEVE)
| Approach                  | Test Accuracy | Inference Time (CPU) | Notes                          |
|---------------------------|---------------|----------------------|--------------------------------|
| SVM (HOG + color)         | 72–78 %       | ~30 ms               | Fastest                        |
| Random Forest             | 76–82 %       | ~50 ms               | Often best classical           |
| XGBoost                   | 78–83 %       | ~60 ms               |                                |
| Custom CNN                | 87–92 %       | ~120 ms              | From scratch                   |
| EfficientNet-B0 (TL)      | 97–99 %       | ~200 ms              | Usually single-model winner    |
| Ensemble (4 models)       | 99.4–99.6 %   | ~400 ms              | Final production model         |
WHATEVER MODEL DECIDED TO IMPLEMENT


### 👥 CREDITS

TO BE CONTINUED AFTER COMPLETION


© 2025 CORE INTELLIGENCE UNT GDGonNUN


⭐ Star this repo if you found it useful!  
Feel free to fork and build your own experiment boplant doctor!
