Ovarian cancer is often diagnosed at advanced stages, leading to poor patient outcomes. This project addresses the need for a more effective early detection system relying only on routine biomarkers by developing a patient risk stratification model using data science. Going beyond binary risk classifications such as ROMA or RMI, the study compares the effectiveness of various machine learning models for classifying patients into risk groups based on a dataset of blood biomarkers and demographic information. The research showed that ensemble methods, specifically XGBoost and Random Forest, achieve superior predictive performance compared to traditional linear models. 

A key contribution of this work is the development of a three-tiered risk stratification system into low, intermediate, and high risk, which offers a more clinically actionable framework. Model interpretability was prioritised through SHAP analysis, which validated that the model's predictions are based on clinically validated relationships, such as CA125, HE4, and age, which were the most influential features. This project serves as an example of a data-driven tool that can assist clinicians in prioritising high-risk patients for further diagnostic tests and added preventative screening for intermediate-risk patients who would have been missed the under binary stratification.

Data was acquired from Kaggle from authors Mi, Q. et al (2020), who completed a study using data from Pekin Union Medical College Hospital. This dataset contains biomarkers (e.g. CA125, HE4, CA72-4, ROMA index), routine blood tests and some demographic information as age and menopause status, focusing on distinguishing benign and malignant ovarian masses. Dataset: https://www.kaggle.com/datasets/saurabhshahane/predict-ovarian-cancer/data .  

Implementation Design Steps 

Firstly, the data will be loaded, and columns will be cleaned to remove extra whitespaces, blanks and other symbols (e.g. ‘>’) to contain a standardised format. Then the data will be handled for missing values depending on the data characteristics. After this, exploratory data analysis (EDA) will be performed to analyse the data and check for correlations.  


Algorithms included in the design  

LR will be the starting ML model as it has higher interpretability (Ahamad et al., 2022) 

RF/ Gradient Boosting (XGBoost, LightGBM) will be the next experiment as it is the best performer in research by Ma et al (2021), Sorayaie, A., et al (2022) and Ahamad et al. (2022).  

SVMs were used in research by both Gui et al. (2025) and Ma et al. (2021), and even though other models performed better, in the research by Gui et al. (2025), the AUC was good.  

Simple NNs will also be explored, following the design by Ma et al. (2021), as these can handle complex relationships in the data. 

To begin ML, the features (X) and the target (Y) will be chosen. Dimensionality Reduction with Principal Component Analysis (PCA) and Feature Selection will be performed to reduce the number of features and retain most variance.   

Next, the data will be split into training and testing by an 80:20 ratio. Hyperparameter tuning (e.g., using Grid Search) and cross-validation (e.g., 5-fold cross-validation) will be performed to ensure robust and generalisable models (Gui, T. et al., 2025). Then the ML models will be applied to analyse the performance.  
Confusion Matrix Components. 

To understand which biomarkers and clinical features are driving each model's predictions, techniques like SHAP (Shapley Additive Explanations) and feature importance_methods (for tree-based models) will be implemented. This is crucial for clinical interpretability and aligns with the practices in the analysed research (Sorayaie Azar, A. et al., 2022; Ahamad et al., 2022).  

In addition to this, a system will be created using the best-performing models and will aim to classify into low, intermediate, and high risk of developing ovarian cancer by predicting probabilities for this risk into a continuous score of probability of malignancy from 0 to 1. This was inspired by research by Laios et al (2022), but it should be noted that currently research into risk stratification alternative to the ROMA and RMI index, is only available for predicting life expectancy of ovarian cancer patients (Laios, A. et al, 2022; Mi, Q. et al, 2021; Sorayaie, A. et al, 2022).   

Conclusion 

This project confirmed that RF, XGBoost and LightGBM, were the best classification models when compared with other models. This suggests they have strong discriminatory power and captured the non-linear relationships present in biomarker and clinical data. SHAP analysis also provided clear and interpretable insights into which features were the most influential predictors of ovarian cancer risk.  

A risk stratification system (low, intermediate, and high risk) was created based on predictions. This framework can prioritise high-risk patients for further diagnostics and intermediate-risk- risk patients for further non-invasive diagnostics; holding potential to improve clinical pathways (eg. ROMA and RMI). 

The next practical step would be to train and validate this model on a larger, more comprehensive NHS dataset to target its 10-year goal, for model generalisability and robustness across different patient populations and healthcare systems.  Performance of the ML models could also be improved by incorporating a wider array of features, including genetic information (e.g., BRCA1/2 status) (Gui et al., 2025), novel biomarkers for improved detection such liquid biopsy, and multiomics (Hong, M. and Ding, D., 2025), and Chronic inflammation blood biomarkers (e.g. CXCL13) (Peres L. et al, 2021; Hong, M. and Ding, D., 2025).   

The integration of a risk stratification model into a clinical pathway would require close collaboration with healthcare professionals to ensure that the defined thresholds and risk categories are truly beneficial for patients and align with current clinical protocols, to ensure model interpretability and actionability. Additionally, it will require robust regulatory and ethical frameworks to ensure the safe, equitable, and responsible deployment of this tool, protecting patient privacy and ensuring accountability. 

In addition to this, women in different age groups should be investigated further to find the best age at which screening would be most helpful, as research by research by Ikram et al (2023) suggested the age of 50, while this project showed that the highest risk was between the ages of 45-65. This will also increase the benefit and resource allocations of the healthcare system, especially when applying for funding for this process improvement. 

In conclusion, this project supports the hypothesis that data science can improve ovarian cancer risk stratification for an earlier diagnosis, creating a clinically interpretable and relevant risk stratification tool for more efficient and earlier detection, which can improve patient outcomes in the future. This can be supported in the future by health programs if provided with funding opportunities such as the National Institute for Health and Care Research (NIHR), Cancer Research UK and the UK Department of Health (Menon, U. et al, 2025). 

 
