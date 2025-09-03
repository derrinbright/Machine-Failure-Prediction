# Data-Driven Machine Failure Prediction  
**Project Status:** Completed  

---

## 1. Project Overview  

This project aimed to develop an automated solution for **predicting machine failures** using sensor data collected from industrial machines. By analyzing a variety of sensor readings and environmental factors, a machine learning model was built to classify whether a machine is likely to fail, enabling proactive maintenance planning to minimize costly downtime.

---

## 2. Background and Rationale  

### Why This Project?  
Unexpected machine failures can cause significant operational disruptions and financial losses. Predictive maintenance powered by machine learning can reduce unplanned downtime by forecasting failures before they occur. This project leverages sensor data and modern classification algorithms to predict machine failure accurately.

### Dataset Description  
The dataset contains **944 records** with sensor readings collected from machines. Key features include footfall counts, air quality (AQ), ultrasonic sensor (USS) data, volatile organic compounds (VOC), temperature, rotational position (RP), input pressure (IP), and a binary failure indicator (`fail`).

---

## 3. Tools and Technologies  

- **Data Manipulation & Analysis:** Python, Pandas, NumPy  
- **Visualization:** Matplotlib, Seaborn  
- **Machine Learning:** Scikit-learn (Random Forest Classifier)  
- **Preprocessing:** StandardScaler for feature scaling  

---

## 4. Methodology: Workflow  

### Phase 1: Data Loading and Exploration  
- Loaded the dataset into a Pandas DataFrame and performed exploratory data analysis (EDA) to understand basic statistics and check for missing values.  
- Confirmed dataset completeness and numerical format for all features.

### Phase 2: Feature Analysis and Selection  
- Performed correlation analysis between each feature and the failure label to identify relevant predictors.  
- Found VOC and AQ strongly correlated with machine failure while `tempMode` and `CS` had negligible correlation and were removed to reduce noise.

### Phase 3: Data Preprocessing and Splitting  
- Separated features (`X`) and target (`y`) variables.  
- Split the data into training (80%) and testing (20%) sets to evaluate model generalizability.  
- Applied `StandardScaler` to normalize features for consistent scale across sensors while avoiding data leakage by fitting scaler only on training data.

### Phase 4: Model Training and Evaluation  
- Trained a **Random Forest Classifier** with 100 estimation trees on the training set to predict failures.  
- Predicted machine failure on test data and evaluated performance using a confusion matrix and accuracy score.  
- Achieved an **accuracy of ~89.4%**, outperforming logistic regression baselines.  

---

## 5. Results and Analysis  

- **Confusion Matrix:**  
  \[
  \begin{bmatrix}
  90 & 12 \\
  8 & 79 \\
  \end{bmatrix}
  \]  
  The model accurately predicted 90 true negatives and 79 true positives, with limited misclassifications.  

- **Model Accuracy:** Approximately **89.4%**, demonstrating effective predictive capability for machine failure.  

- **Feature Importance:** VOC was identified as the most informative sensor reading correlating with failures, consistent with domain knowledge about environmental impact on machine health.

---

## 6. Conclusion  

This project successfully implemented a **machine learning pipeline** for machine failure prediction using sensor data. By preprocessing sensor signals, selecting relevant features via correlation, and training a Random Forest classifier, it provided a **robust predictive model** with high accuracy.  

This model can empower maintenance teams to anticipate and address machine issues proactively, reducing operational disruption and improving productivity. The workflow is readily extendable to larger or related industrial datasets for wider predictive maintenance applications.

---
