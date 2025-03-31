# Pet_Activity_Analysis-

 Introduction

The purpose of this project was to develop and deploy an AI-based activity recognition system using wearable device step data. The system classifies different activities such as Walking, Running, Sprinting, Eating, Drinking, Lying, and Sitting using three models:

Random Forest Classifier (RF)

Convolutional Neural Network (CNN)

Hybrid CNN (CNN + Statistical Features)

The goal was to achieve high classification accuracy by improving data preprocessing, handling missing values, removing outliers, and optimizing model performance.

2. Data Collection & Preprocessing

2.1 Data Collection

The dataset was generated synthetically based on step counts, energy expended, and duration. It contained timestamps and categorical activity labels.

2.2 Handling Missing Values

The dataset contained missing values, which were handled by replacing them with the median of each numeric feature to preserve data integrity.

2.3 Outlier Removal Using IQR

Outliers were detected and removed using the Interquartile Range (IQR) method, ensuring that extreme values did not distort the model’s learning process.

2.4 Feature Engineering

Additional statistical features were created to improve model performance:

Mean, Variance, Standard Deviation, Skewness, and Kurtosis of step counts over a rolling window.

These features captured the temporal patterns of step data for better classification.

2.5 Label Encoding

Categorical activity labels were converted into numerical format using Label Encoding.

2.6 Feature Scaling & Class Balancing

Features were scaled using MinMaxScaler.

SMOTE (Synthetic Minority Over-sampling Technique) was applied to balance the dataset, preventing bias toward overrepresented activities.

3. Model Development

3.1 Random Forest Classifier (RF)

A 300-tree Random Forest model was trained with a maximum depth of 20 and a minimum sample split of 5.

Random Forest was chosen for its robustness in handling mixed feature types and its interpretability.

3.2 Convolutional Neural Network (CNN)

A 1D CNN model was designed to capture patterns in step sequences.

Architecture:

Two Conv1D layers with Batch Normalization and Dropout

A Flatten layer followed by Dense layers

Output layer with softmax activation for multi-class classification

The CNN model was trained using the Adam optimizer with sparse categorical cross-entropy loss.

3.3 Hybrid CNN (CNN + Statistical Features)

This model combined CNN’s ability to extract spatial features with statistical feature analysis.

The architecture was similar to CNN but included engineered features to retain global time-series information.

4. Model Evaluation

Each model was evaluated on test data using:

Accuracy Score

Classification Report (Precision, Recall, F1-score)

Confusion Matrix

A visualization of accuracy comparisons among RF, CNN, and Hybrid CNN was provided to highlight performance differences.

5. Deployment Strategy

The trained models were prepared for deployment in real-world applications. The deployment strategy included:

Integration with Wearable Device Firmware for real-time activity recognition.

Cloud-based inference for scalability and remote updates.

Mobile App Connectivity via API, allowing users to access insights from their smart devices.

Over-the-Air (OTA) Updates, enabling continuous model improvements over time.

6. Additional Visualizations

To enhance interpretability and presentation, the following visualizations were added:

Class distribution plots (Before and After SMOTE)

Accuracy comparisons of all three models

Confusion matrices for detailed error analysis

7. Conclusion

Through systematic data preprocessing, feature engineering, and model development, we achieved a classification accuracy of ~70%. Further optimization, such as hyperparameter tuning, additional feature selection, and alternative activation functions, could be explored to improve results.

This report summarizes the methodology and process followed in developing the AI-based step data analysis system. The results demonstrate the feasibility of using machine learning and deep learning models for activity classification in wearable devices.
