# Student Health Risk Analysis

## 📌 Business Overview
Universities and health organizations face an ongoing challenge in identifying at-risk students to provide timely, effective interventions. The primary objective of this project is to analyze student data and identify key lifestyle, academic, and physiological drivers that contribute to a student's `Health_Risk_Level`. By identifying the primary factors behind health risks, institutions can strategically allocate resources, design targeted health programs, and ultimately improve overall student well-being.

## 💡 Business Q&A & Actionable Insights
**Q1: What is the most significant factor placing students at a high health risk?**
- **A:** Stress levels emerged as the most significant predictor of health risk across all analyses. Both self-reported stress and biosensor data heavily dominated the predictive models. 
- **Action:** Universities investing in targeted stress management interventions and accessible mental health support could see improvement in student health.

**Q2: Do heavy academic workloads (study/project hours) directly cause higher health risks?**
- **A:** The relationship is nuanced; while median study and project hours were relatively stable across all risk levels, project hours contained the highest number of statistical outliers. Higher academic loads may contribute to increased stress levels, which in turn affects health. 
- **Action:** Monitor students taking on extreme project loads and ensure they are balancing academic responsibilities with stress management strategies.

**Q3: How critical is sleep quality to a student's overall health classification?**
- **A:** Poor sleep quality was consistently highlighted as an important factor impacting health risk levels and emerged as one of the top predictive features. 
- **Action:** Campus initiatives promoting healthy sleep habits could serve as highly effective preventative measures.

**Q4: How can we optimize the allocation of our wellness resources across the student body?**
- **A:** Chi-Square testing revealed that gender was strongly associated with both physical activity and sleep quality. Additionally, physical activity showed a clear correlation with health risk levels. 
- **Action:** Interventions tailored to specific demographics may be more beneficial and effective than generalized campus-wide campaigns.

**Q5: How should we handle "borderline" or moderate-risk student assessments?**
- **A:** My predictive modeling occasionally misclassified High-risk instances as Moderate. Misclassifying a high-risk student could lead to missed critical interventions. 
- **Action:** Any real-world deployment of these risk assessments must prioritize a recall-focused approach to ensure high-risk cases do not slip through the cracks.

## 📊 Exploratory Data Analysis (EDA)
Thorough EDA was conducted to uncover patterns and guide the business strategy:
* **Categorical Associations:** Chi-Square testing confirmed strong statistical associations between `Health_Risk_Level` and both Physical Activity and Sleep Quality. 
* **Distribution Insights:** Stress levels showed significant variation across risk levels, indicating a potential relationship between higher stress and increased health risk.
* **Correlation Analysis:** Pearson and Spearman correlation analyses revealed no significant correlations among numerical features, simplifying the analysis by showing no need to account for interdependencies between variables. 

## 🧹 Data Cleaning & Preprocessing
To ensure robust analysis, the initial dataset of 1,000 student instances underwent rigorous preparation:
* **Quality Checks:** Verified the dataset contained zero missing values and zero duplicate records. Dropped non-predictive identifiers.
* **Outlier Handling:** Utilized the Interquartile Range (IQR) method to detect anomalies, ultimately removing 21 outlier instances (primarily in Heart Rate and Project Hours) to prevent skewed analysis.
* **Data Preparation:** Converted object data types to categorical variables to ensure the data was in a suitable format for subsequent analysis. Standardized numerical features and applied one-hot encoding to categorical features for modeling consistency.

## 🤖 Predictive Modeling (Machine Learning)
To validate the findings from the EDA, three tree-based classification models were trained and evaluated: Decision Tree, Random Forest, and XGBoost. 
* **Model Performance:** After hyperparameter tuning using `GridSearchCV`, the models performed exceptionally well on unseen test data, with the XGBoost model achieving 100% accuracy, precision, recall, and F1-scores. 
* **Feature Importance Validation:** The models confirmed the EDA findings. Extracted feature importance metrics consistently revealed that predictions were heavily dominated by just four features: `Stress_Level_Self_Report`, `Stress_Level_Biosensor`, `Sleep_Quality_Poor`, and `Physical_Activity_High`. 

## 🛠️ Tech Stack
* **Language:** Python
* **Data Manipulation:** Pandas, NumPy
* **Data Visualization:** Matplotlib, Seaborn
* **Statistical Analysis:** SciPy (Chi-Square Testing)
* **Machine Learning:** Scikit-learn (Decision Trees, Random Forest, GridSearchCV), XGBoost

## 📁 Repository Structure
```text
├── data/
│   └── student_health_data.csv       # Raw dataset 
├── notebooks/
│   ├── 01_Clean_and_EDA.ipynb        # Data cleaning and exploratory analysis
│   └── 02_Tree_Based_Models.ipynb    # Machine learning and feature importance
├── README.md                         # Project overview and insights
```

---






