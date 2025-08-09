# Supply Chain Analytics Project

## **Project Goal**
**Demand Forecasting of Products** — the art and science of predicting future customer demand to improve inventory management, supply chain efficiency, and business decision-making.

---

## **Dataset**

- **Source:** [UCI Machine Learning Repository – Online Retail Dataset](https://archive.ics.uci.edu/ml/datasets/online+retail)  
- **Type:** Multivariate, Sequential, Time-Series  
- **Scope:** Transactions between 2010–2011 for a UK-based online retail gift shop  
- **Key Attributes:**  
  - `InvoiceNo`, `StockCode`, `Description`, `Quantity`, `InvoiceDate`, `UnitPrice`, `CustomerID`, `Country`

**Dataset Highlights:**  
- Rich combination of **numerical and categorical attributes**.  
- Ideal for exploring customer behavior patterns and demand trends.

---

## **Data Exploration & Feature Engineering**

### **Correlation Analysis**
<p align="center">
<img src="https://github.com/Oprishri/Supply-Chain-Analytics-Project/blob/master/images/correlation.PNG" alt="Correlation Heatmap" width="600" height="300">
</p>

### **New Features Created**
- **Product Type**: Extracted nouns from `Description` using POS tagging.  
- **Colour Type**: Identified product colors from `Description`.  
- **Revenue**: Calculated as:  
  \[
  \text{Revenue} = \text{UnitPrice} \times \text{Quantity}
  \]

---

## **Three-Step Machine Learning Approach**

Our pipeline follows a **Clustering → Classification → Prediction** strategy.

### **1. Clustering**
**Challenge:**  
- Mixed attributes (**numerical + categorical**)  
- Preserving the significance of categorical features without one-hot encoding noise  

**Solution:**  
- **Algorithm:** `K-Prototypes` — an extension of k-means for mixed data  
- **Advantages:**  
  - Handles numeric and categorical attributes simultaneously  
  - Maximizes intra-cluster similarity  
  - Maintains computational efficiency  

**Output:**  
- Cluster IDs assigned to each record — later used as labels for classification.

---

### **2. Classification**
- **Goal:** Predict the cluster for new incoming records.  
- **Algorithm Used:** **Linear SVM** — provided high accuracy in mapping new data points to their respective clusters.

---

### **3. Demand Prediction**
- **Target Variable:** `Quantity`  
- **Approach:**  
  - Combined all engineered features + cluster labels  
  - Split dataset into training and testing sets  
  - Applied regression models  
- **Best Performer:** **Random Forest Regressor** — delivered strong predictive accuracy for demand forecasting.

---

## **Conclusion**

- **Preprocessing** ensured cleaner and more meaningful model inputs.  
- **Feature Engineering** enriched the dataset with valuable business insights (product type, color, revenue).  
- **Three-Step Pipeline** provided:  
  1. Segmentation of products/customers (Clustering)  
  2. Quick classification of new data points  
  3. Accurate quantity forecasting for demand planning  
- This methodology can help businesses **optimize inventory, reduce costs, and improve customer satisfaction**.

---

## **Project Structure**
```
Supply-Chain-Analytics-Project/
│
├── data/ # Raw and processed datasets
├── images/ # Visualizations and plots
├── notebooks/ # Jupyter notebooks for EDA and modeling
├── src/ # Source code for clustering, classification, and prediction
├── README.md # Project documentation
└── requirements.txt # Python dependencies
```

---

## **Installation & Usage**

1. **Clone the repository**
   ```bash
   git clone https://github.com/<your-username>/Supply-Chain-Analytics-Project.git
   cd Supply-Chain-Analytics-Project




