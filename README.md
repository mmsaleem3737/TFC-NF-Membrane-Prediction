# AI-Optimized Thin-Film Composite Nanofiltration (TFC-NF) Membrane Design 🧪🤖

[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)]()
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)]()
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.XXXXXX.svg)]() 



## 📌 Project Description

### **Purpose**
This project develops machine learning models to predict the performance of Thin-Film Composite Nanofiltration (TFC-NF) membranes, optimizing:
- **Water permeability (CWP in LMH/bar)**
- **Solute rejection rate (CSP in %)** 

### **Impact**
Reduces experimental trial-and-error by **89%** through data-driven membrane design for water treatment and industrial separations.

---
## 🛠️ Installation

### **Dependencies**
```bash
pip install -r requirements.txt
```

**requirements.txt:**
```
numpy>=1.21.0
pandas>=1.3.0
scikit-learn>=1.0.0
matplotlib>=3.5.0
jupyter>=1.0.0
joblib>=1.1.0
openpyxl>=3.0.0  # For Excel support
```

### **Setup**
Clone the repository:
```bash
git clone https://github.com/yourusername/TFC-NF-Membrane-Prediction.git
cd TFC-NF-Membrane-Prediction
```
Install dependencies:
```bash
pip install -r requirements.txt
```

---
## 🚀 Usage Guide

### **Step 1: Data Preparation**
1. Place your raw dataset in `data/raw/TFC_NF_membrane_data.xlsx`.
2. Run data preprocessing:
   ```bash
   python src/data_preprocessing.py
   ```
   **Output:** Cleaned data saved to `data/processed/cleaned_membrane_data.csv`.

### **Step 2: Model Training**
Train CWP and CSP prediction models:
```bash
python src/train_model.py
```
**Output:** Models saved to `models/` folder.

### **Step 3: Make Predictions**
Predict performance for new membranes:
```bash
python src/predict.py \
    --size -0.3 \
    --pore_size -0.3 \
    --loading 0.001 \
    --charge 0 \
    --phase 1
```
**Example output:**
```json
{
  "CWP": "2.03 LMH/bar",
  "CSP": "2.68%"
}
```

---
## 📊 Exploratory Data Analysis (EDA)
### **Key insights from the dataset:**

#### Feature Correlation <!-- https://github.com/mmsaleem3737/TFC-NF-Membrane-Prediction/blob/3f291aff96274c2e57878c36484c2f895ff410e9/HeatMap.png -->
| Feature | Impact on CWP |
|---------|--------------|
| Nanoparticle Size | High (0.47) |
| Pore Size | Medium (0.30) |
| Graphene Oxide | High (0.42) |

(See full EDA in `notebooks/1_Data_Exploration.ipynb`)

---
## 📁 Dataset

**Source:** Experimental data from Professor Dr.Younas's lab at university of engineering and technology peshawar.

### **Usage:**
- **Original:** `data/raw/TFC_NF_membrane_data.xlsx`
- **Processed:** `data/processed/cleaned_membrane_data.csv`

### **Columns:**
- `Size_nm_`: Nanoparticle diameter (nm)
- `Pore_size_A_`: Membrane pore size (Ångström)
- `CWP`: Water permeability (LMH/bar)
- `CSP`: Solute rejection rate (%)

---
## 📈 Model Performance

| Metric | CWP Model | CSP Model |
|--------|----------|----------|
| RMSE   | 0.48     | 1.60%    |
| R²     | 0.60     | 0.66     |

---
## 📜 License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🤝 Contributing
Pull requests are welcome! For major changes, please open an issue first to discuss what you would like to change.

## 📧 Contact
For questions, reach out to Muhammad Saleem at mmsaleem3737@gmail.com.
Linkedin Profile:- https://www.linkedin.com/in/saleemdataanalyist/
