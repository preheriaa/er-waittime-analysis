# 🏥 ER Wait Time Prediction Using Big Data  

## 📌 Overview  
This project investigates the key hospital-related factors influencing **Emergency Department (ED) wait times** and develops predictive models to estimate total wait time. Using a simulated dataset of **5,000 patient visits (2024)**, the study applies **big data analytics and machine learning** to uncover insights into operational inefficiencies and propose actionable strategies to improve patient flow and satisfaction.  

The work was completed as part of the **COMP SCI 7209 – Big Data Analysis and Project** at the University of Adelaide.  

---

## 🎯 Research Question  
**Which hospital-related factors have the greatest effect on emergency room wait times, and how can these insights help reduce delays and improve patient experiences?**  

---

## 📂 Project Structure  

- **Part A – Question Formation & Exploratory Analysis**  
  - Defined the research question  
  - Conducted initial data cleaning and exploratory data analysis (EDA)  
  - Identified key temporal and operational patterns  

- **Part B – Big Data Analysis**  
  - Feature engineering (time of day, day of week, season)  
  - Visualisation of relationships between wait times, urgency, and staffing  
  - Identified early correlations (e.g., longer waits on Mondays, afternoons, and winter)  

- **Part C – Modelling**  
  - Built predictive models (Linear Regression, Random Forest)  
  - Applied preprocessing pipelines (scaling, encoding, splitting)  
  - Performed hyperparameter tuning with GridSearchCV  
  - **Tuned Random Forest** achieved:  
    - RMSE = **18.37 minutes**  
    - R² = **0.9274**  

- **Part D – Final Report**  
  - Combined analysis, modelling, and findings into a comprehensive research report  
  - Highlighted key predictors: **Urgency Level, Nurse-to-Patient Ratio, Time of Day**  
  - Proposed practical recommendations for hospital scheduling and staffing  

---

## 📊 Dataset  

- **Name:** ER Wait Time Dataset  
- **Source:** [Kaggle – ER Wait Time (Creative Commons, 2025)](https://www.kaggle.com/datasets/rivalytics/er-wait-time)  
- **Records:** 5,000 simulated patient visits  
- **Features:** 20 columns, including hospital region, urgency level, nurse-to-patient ratio, specialist availability, and patient outcomes  

⚠️ *Note:* The dataset is **simulated** but reflects realistic hospital patterns (e.g., busier Mondays, critical patients prioritised, seasonal demand).  

---

## 🔧 Methodology  

1. **Data Preprocessing**  
   - Date parsing (hour, day, month)  
   - One-hot encoding for categorical variables  
   - Standard scaling for numerical features  
   - Train-test split (80/20)  

2. **Feature Engineering**  
   - Temporal variables: hour, day of week, season  
   - Operational metrics: nurse-to-patient ratio, specialist availability, bed count  

3. **Modelling**  
   - Baseline: Linear Regression  
   - Advanced: Random Forest (with hyperparameter tuning)  

4. **Evaluation Metrics**  
   - Root Mean Squared Error (RMSE)  
   - R² (Coefficient of Determination)  
   - Residual and prediction plots  

---

## 📈 Key Findings  

- **Urgency level** is the strongest predictor – critical patients are seen sooner.  
- **Nurse-to-patient ratio** has a major effect – lower ratios significantly reduce waits.  
- **Time of day and day of week** matter – afternoons and Mondays are the busiest.  
- **Specialist availability** reduces delays, suggesting telemedicine could be a useful support.  
- The tuned **Random Forest** model provided robust and accurate predictions, outperforming linear models.  

---

## ✅ Recommendations  

- Increase **nurse staffing** during peak demand (e.g., Monday afternoons).  
- Align **specialist schedules** with high-volume periods.  
- Use **telehealth/virtual consults** to ease specialist shortages.  
- Implement **predictive dashboards** for real-time wait time forecasting.  

---

## 📚 References  
Key references include:  
- Munro et al. (2006) – ED wait time reduction strategies  
- Drennan et al. (2024) – Nurse staffing and care quality  
- Kirby et al. (2024) – Triage acuity and wait time differences  
- GeeksforGeeks (2025) – Preprocessing & Random Forest methods  
- Creative Commons (2025) – ER Wait Time Dataset  

*(Full reference list is available in the final report.)*  

---

## 🚀 How to Run  

1. Clone the repository:  
   ```bash
   git clone https://github.com/your-username/Big-Data-Analysis-and-Project.git
   cd Big-Data-Analysis-and-Project
   ```

2. Install dependencies:  
   ```bash
   pip install -r requirements.txt
   ```

3. Open the Jupyter notebooks:  
   ```bash
   jupyter notebook
   ```

4. Run files in order:  
   - **Part A – Exploratory Analysis.ipynb**  
   - **Part B – Big Data Analysis.ipynb**  
   - **Part C – Modelling.ipynb**  
   - Review final results in **Part D – Report.pdf**  

---

## 📎 Replication Package  

- Full code and documentation available in this repository  
- Dataset available on Kaggle (linked above)  
- Final IEEE-style report included in `/reports`  

---

## 👨‍💻 Author  

**Prashant Shrestha**  
Master of Data Science, University of Adelaide  
