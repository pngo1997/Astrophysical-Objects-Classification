# 🌌 Astrophysical Objects Classification  

## 📜 Overview  
This project applies **machine learning (ML) techniques** to classify **astrophysical objects** using observational data from the **Large Synoptic Survey Telescope (LSST)**. By leveraging **time-series and static numerical features**, we aim to develop an accurate model for classifying celestial objects, such as **comets and asteroids**, based on their spatial positions, light curves, and motion.

## 🎯 Problem Explanation  
The **LSST dataset** consists of **astronomical time-series data** collected through **optical sky scanning**. The telescope tracks the **brightness and motion** of celestial objects to support cosmic mapping and asteroid threat assessments.

### **Challenges in Classification**  
1. **Complex Feature Representation**:  
   - The dataset contains both **static** (e.g., position, redshift) and **time-series** (e.g., brightness over time) attributes.  
   - Integrating these features for classification is **non-trivial**.  

2. **Imbalanced Classes**:  
   - Certain astrophysical objects are overrepresented, leading to **biased model predictions**.  

3. **Selection of the Best ML Model**:  
   - Decision trees, boosting methods, and neural networks have **different strengths** for time-series and tabular data.  
   - We evaluate **multiple models** to determine the best approach.  

📌 **Dataset**: LSST Photometric Time Series (PLAsTiCC Competition)  
🔢 **Observations**: 4,925 total (2,459 train | 2,466 test)  
📊 **Classes**: 16 astrophysical object types  

## 📊 Data Preprocessing & Feature Engineering  

### **1️⃣ Dataset Overview**  
The dataset includes **two types of data**:  
| **Feature Type** | **Description** |
|----------------|--------------------------------|
| **Static Features** | Spatial attributes (RA, DEC, Galactic coordinates) |
| **Time-Series Features** | Brightness variations over time |

### **2️⃣ Handling Class Imbalance**  
- **Applied class weighting** to ensure fair representation.  
- **Downsampling techniques** adjusted sample distribution.  

### **3️⃣ Feature Engineering**  
- **Rolling time-window transformations** on flux values.  
- **Feature selection** using correlation analysis.  
- **Normalization & scaling** applied for neural network compatibility.  

## 🔍 Exploratory Data Analysis (EDA)  

### **1️⃣ Meta Data (Static Features)**  
- **Right Ascension (RA) vs. Galactic Longitude (GL)** shows an **inverse parabolic trend**.  
- **High variance in brightness motion data** across objects.  

📊 **EDA Visualization**:  
- **Feature correlation heatmaps**  
- **Class distribution histograms**  
- **Light curve plots of six sample objects**  

## 🤖 Machine Learning Models  

### **1️⃣ Random Forest (RF) 🌲**  
✔️ **Strengths**:  
- Handles **high-dimensional data** well.  
- Provides **high accuracy & interpretability**.  

📊 **Results**:  
- **Train Accuracy**: **97%** | **Log Loss**: **1.05**  
- **Downsampled Accuracy**: **91%** | **Log Loss**: **3.17**  

### **2️⃣ Gradient Boosting (GB) 🚀**  
✔️ **Strengths**:  
- **Reduces bias** via sequential boosting.  
- More effective in handling **complex relationships**.  

📊 **Results**:  
- **Train Accuracy**: **68%** | **Log Loss**: **11.64**  
- **Downsampled Accuracy**: **65%** | **Log Loss**: **12.53**  

### **3️⃣ Adaptive Boosting (AB) 🏋️**  
✔️ **Strengths**:  
- Assigns **weights to observations**, improving classification of hard-to-predict samples.  

📊 **Results**:  
- **Train Accuracy**: **46%** | **Log Loss**: **19.54**  
- **Downsampled Accuracy**: **23%** | **Log Loss**: **7.78**  

### **4️⃣ Neural Networks (NNs) 🧠**  
✔️ **Strengths**:  
- Captures **complex temporal dependencies** in time-series data.  
- Uses **LSTM layers** for time-dependent pattern recognition.  

📊 **Results**:  
- **Train Accuracy**: **46%**  
- **Weighted Accuracy**: **59%**  
- **Log Loss**: **9.6**  

## 🏆 Best Performing Model  
📌 **Random Forest (RF) is the most effective model**:  
- **Highest accuracy (97%)** on full train data.  
- **Performs well with both static & time-series features**.  
- **Faster training time** compared to Boosting & Neural Networks.  

🚀 **Key Observations**:  
- **Feature selection improved model performance** by **removing redundant features**.  
- **Downsampling maintained class distribution** while improving computational efficiency.  
- **Neural Networks struggled with time complexity and performance tuning**.
  
## 📢 Key Findings & Recommendations  

✅ **Key Insights**:  
- **Light curve patterns are highly predictive** of object classification.  
- **Feature selection significantly improves classification accuracy**.  
- **Class imbalance correction is essential** for fair model evaluation.  

🔧 **Recommended Future Work**:  
- 📊 **Test alternative deep learning architectures** (CNNs for feature extraction).  
- ⚡ **Optimize feature engineering** for time-series processing.  
- 🔬 **Use SMOTE for class balancing** instead of downsampling.  

## 🚀 Technologies Used  
🛠 **ML Frameworks**:  
- **Python (Scikit-learn, TensorFlow, Keras)**  
- **Pandas, NumPy** for preprocessing  
- **Matplotlib, Seaborn** for visualization  

📡 **Dataset**: [LSST Photometric Time Series Data (PLAsTiCC)](https://timeseriesclassification.com/description.php?Dataset=LSST)  
