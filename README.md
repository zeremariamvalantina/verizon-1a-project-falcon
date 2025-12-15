# 🦅 Project Falcon - Verizon
## AI-Driven Bird & Nest Detection on Cell Towers (YOLOv8)

## 📌 Overview
**Project Falcon** is an end-to-end computer vision system developed as part of the **Verizon AI Studio Final Project** for **Break Through Tech**, an AI fellowship hosted by **Cornell Tech**. The project applies deep learning to automatically detect **birds, bird nests, and bird species** on cell towers using image data.

The system is designed to help telecommunications providers:
- Protect avian wildlife
- Maintain regulatory compliance with federal wildlife laws
- Reduce operational delays and inspection costs
- Improve tower maintenance planning through early, automated detection

Each year, **4–40 million bird deaths** are attributed to cell towers. Project Falcon demonstrates how AI can be used responsibly to mitigate this impact while improving operational efficiency.

---

## 🎯 Objectives
- Detect **occupied and unoccupied bird nests** on cell towers  
- Detect **birds** and optionally classify **bird species**
- Automatically flag potential nesting sites for proactive action
- Reduce reliance on manual tower inspections
- Support environmental stewardship initiatives

---

## 🌟 Project Highlights
- Built an **end-to-end YOLOv8 pipeline** from raw data ingestion to model evaluation
- Cleaned and standardized **multiple heterogeneous datasets**
- Achieved **high-precision nest detection (95%+)**
- Demonstrated that **data quality outweighed model complexity**
- Delivered clear **business and conservation impact**

---

## 👥 Team
Developed by a cross-university team as part of **Verizon AI Studio**:

| Name               | GitHub Handle | Contribution |
|--------------------|--------------|--------------|
| Justin Gajewski (Stevens Institute of Technology) | [@JustinGaj](https://github.com/JustinGaj) | Project coordination, model research, data cleaning, preprocessing support |
| Ayooluwa Olotu (Howard University) | [@ayoolotu](https://github.com/ayoolotu) | Data cleaning, annotation standardization, dataset validation |
| Aastha Oza (University of Houston) | [@AasthaOza21](https://github.com/AasthaOza21) | Dataset exploration, data preprocessing, augmentation strategies |
| Valantina Zeremariam (Vassar College) | [@zeremariamvalantina](https://github.com/zeremariamvalantina) | Dataset integration, YOLOv8 training, model refinement, metrics analysis |
| Kalyn Bui (San Jose State University) | [@kalynb700](https://github.com/kalynb700) | Label standardization, evaluation analysis, performance tuning, evaluation metrics |
| Anahi Perez (Emory University) | [@aperez404](https://github.com/aperez404) | Project coordination, dataset exploration, data cleaning, preprocessing support, augmentation strategies |
| Chris Dollo (University of Maryland, Baltimore County) | [@chrisdollo](https://github.com/chrisdollo) | Dataset exploration, data preprocessing, augmentation strategies |
| Kenzy Ibrahim (George Mason University) | [@Kenzyi2024](https://github.com/Kenzyi2024) | Dataset integration, YOLOv8 training, model refinement, metrics analysis |

---

## 👩🏽‍💻 **Setup and Installation**

**How to reproduce our results:**

* How to clone the repository
  ```bash
   git clone https://github.com/JustinGaj/verizon-1a-project-falcon.git
   cd verizon-1a-project-falcon
  
* How to install dependencies
  Make sure you have Python 3.8+
  pip install -r requirements.txt

* How to set up the environment
  ``` bash
  python -m venv venv
  source venv/bin/activate  # macOS/Linux
  venv\Scripts\activate   # Windows
* How to run the notebook or scripts
  jupyter notebook  14k_model_run.ipynb
                    cell_tower_mini_model.ipynb
                    speciescleaning.ipynb

---

## 🗂️ Datasets  
Our project leverages multiple datasets, merged and standardized into YOLOv8 format:  
- [Roboflow: bird-nest-dataset-kpvdq](https://universe.roboflow.com/datasets-wgkry/bird-nest-dataset-kpvdq/browse?queryText=&pageSize=50&startingIndex=0&browseQuery=true)  
- [Hugging Face: JotDe/birds](https://huggingface.co/datasets/JotDe/birds)  
- [Hugging Face: Francesco/cell-towers](https://huggingface.co/datasets/Francesco/cell-towers)  
- [Hugging Face: Ez-Clap/bird-species](https://huggingface.co/datasets/Ez-Clap/bird-species)  

Each dataset varied significantly in quality, annotation style, and format, requiring extensive preprocessing and validation.

---

## 🔧 Data Preparation Pipeline
A major focus of the project was **data quality and standardization**, which had a greater impact on model performance than architecture complexity.

### Key Preparation Steps
- Converted all annotations to YOLOv8 `.txt` format
- Standardized labels (`bird`, `nest`, species-level classes)
- Removed corrupted, duplicated, blurry, and incompatible images
- Applied augmentation:
  - Horizontal flips
  - Small rotations
  - Brightness & contrast adjustments
  - YOLOv8 mosaic augmentation
- Split datasets into Train (80%), Validation (10%), Test (10%)

**Insight:** Proper cleaning and formatting had a greater effect on model performance than increasing model complexity.

Tools used: OpenCV, Pillow, Roboflow, Google Colab

---
## 🧠 Model Architecture
Project Falcon uses **YOLOv8 (You Only Look Once)** — a state-of-the-art real-time object detection model optimized for:
- High detection accuracy
- Low inference latency
- Scalability across large image pipelines

### Supported Tasks
1. **Nest Detection** (Binary Object Detection)
2. **Bird Detection**
3. **Bird Species Classification** (Optional Extension)

---
## 🧠 Model Development
Project Falcon uses **YOLOv8 (You Only Look Once)**, a state-of-the-art real-time object detection model chosen for its balance of speed, accuracy, and scalability.

### Supported Tasks
1. **Nest Detection** (Binary Object Detection)
2. **Bird Detection**
3. **Bird Species Classification** (Optional Extension)

### Training Approach
- Trained YOLOv8 models on cleaned and augmented datasets
- Tuned confidence thresholds to reduce false positives
- Evaluated predictions against ground-truth annotations
- Iteratively refined preprocessing and training configurations

---

## 📊 Results & Key Findings

### 🪹 Nest Detection (Binary Classification)
- **Precision:** 95.41%  
- **Recall:** 85.01%  
- **Accuracy:** 81.82%  
- **F1 Score:** 89.91%

### 🐦 Bird Detection & Species Classification
- **Top-1 Accuracy:** 75.9%  
- **Top-5 Accuracy:** 94.7%  
- **Detection Recall:** 92.8%

A **40% confidence-gating mechanism** was implemented to suppress low-confidence predictions and reduce false positives on ambiguous images (e.g., camouflage, blur).

---

## 🛠️ Technologies Used
- YOLOv8 (Ultralytics)
- Python
- OpenCV
- Pillow
- Google Colab
- Roboflow
- Hugging Face Datasets
- GitHub

All tools reflect **industry-standard workflows** for scalable computer vision systems.

---

## 🚀 Next Steps
Planned and proposed extensions include:
- Detecting whether a **cell tower structure** is present before wildlife detection
- Integrating **audio-based cues** for bird species classification
- Combining nest detection and species classification into a unified pipeline
- Expanding datasets with **region-specific bird species**
- Developing a **user-friendly interface** for field teams

---

## 🙏 Acknowledgments

We would like to extend our sincere thanks to the individuals who supported and guided this project throughout the Verizon AI Studio program:

- **Audra Zook** — AI Studio Coach  
- **Teena Thankachan** — Challenge Advisor  
- **Deepa Thazhathu Veetil** — Challenge Advisor  
- **Ari Moreno** — Alumni Advisor  
- **Lara Sabha** — Alumni Advisor  

Their mentorship, technical guidance, and feedback were instrumental in shaping the direction, rigor, and impact of Project Falcon.
