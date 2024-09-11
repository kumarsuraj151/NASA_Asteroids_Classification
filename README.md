# NASA Asteroids Classification

**Team Members:**
- **Iragavarapu Sai Pradeep** (AI21BTECH11013)
- **Suraj Kumar** (AI21BTECH11029)

## Abstract

Asteroids, remnants of our solar system’s formation, hold valuable clues about its history and composition. They exist in the asteroid belt between Mars and Jupiter and possess properties like diameter, relative velocity, composition, and orbital characteristics. This project aims to classify asteroids into hazardous and non-hazardous categories based on these properties. By analyzing features such as size, orbit characteristics, and relative velocity, we can prioritize asteroids for further observation and potential mitigation strategies. This contributes to planetary defense efforts by identifying and understanding potential threats from asteroids.

## 1. Introduction

### 1.1 Background and Motivation

Celestial objects like asteroids could pose potential threats to our planet. Space organizations like ISRO, NASA, and CNSA work diligently to gain insights about these asteroids to improve future defense strategies. Important features such as size, velocity, and eccentricity are key in understanding these celestial objects.

### 1.2 Objective

The objective of this project is to focus on critical features of asteroids to determine whether these objects could pose a hazard to Earth.

### 1.3 About the Dataset

We used the [NASA Asteroids Classification dataset](https://www.kaggle.com/datasets/shrutimehta/nasa-asteroids-classification) from Kaggle. This dataset contains more than 30 features for approximately 4000 asteroids and is officially released by NASA.

## 2. Exploratory Data Analysis (EDA)

### 2.1 Data Cleaning and Preprocessing

Before analysis, we ensured data quality by handling missing values and correcting inconsistencies. The dataset had no missing values. Redundant columns, such as those representing the same quantity in different units, were streamlined by selecting one metric for each feature.

### 2.2 Univariate Analysis

- **Estimated Diameter of Asteroids (in KM):**
  Most asteroids have a diameter of less than 5 KM, with fewer asteroids having larger diameters.

  ![Histogram of Estimated Diameter Max (in KM)](path/to/histogram_diameter.png)

- **Absolute Magnitude of Asteroids:**
  Most asteroids have moderate brightness, with a few having extreme values.

  ![Histogram of Absolute Magnitude](path/to/histogram_magnitude.png)

- **Inclination of Asteroids:**
  Most asteroids have inclinations between 0 and 30 degrees, with a peak around 3.74 degrees.

  ![Histogram of Inclination](path/to/histogram_inclination.png)

- **Orbital Period of Asteroids:**
  The number of asteroids increases and then decreases with increasing orbital period.

  ![Histogram of Orbital Period](path/to/histogram_orbital_period.png)

### 2.3 Bivariate Analysis

- **Estimated Diameter in KM(max) and Absolute Magnitude:**
  Larger asteroids tend to have lower absolute magnitudes, indicating they reflect more sunlight.

  ![Scatter Plot between Estimated Diameter in KM(max) and Absolute Magnitude](path/to/scatter_diameter_magnitude.png)

- **Aphelion Distance and Eccentricity:**
  As eccentricity increases, aphelion distance and its variance also increase.

  ![Scatter Plot between Aphelion Distance and Eccentricity](path/to/scatter_aphelion_eccentricity.png)

### 2.4 Dimensionality Reduction

We applied Principal Component Analysis (PCA) to retain components that explain 99% of the total variance, resulting in 14 components.

### 2.5 Data Visualization Analysis

- **KDE on Eccentricity of Asteroids:**
  Most asteroids have moderate eccentricities, with a peak around 0.4.

  ![KDE Plot of Eccentricity](path/to/kde_eccentricity.png)

- **Variation of Eccentricity with Aphelion and Perihelion Distances:**
  Asteroids with smaller aphelion distances tend to have lower eccentricity.

  ![Variation of Eccentricity with Aphelion and Perihelion Distances](path/to/variation_eccentricity.png)

- **Correlation Heat Map:**
  High correlation between Orbital Period and Aphelion Distance.

  ![Correlation Heat Map](path/to/correlation_heatmap.png)

## 3. Classification Task

We applied several classification methods including Logistic Regression, Ridge Regression, Support Vector Machine (SVM), Random Forest, and Decision Tree. The dataset was split into training and testing sets:

| Dataset Split  | Total Samples | Hazardous NEOs | Non-Hazardous NEOs |
|----------------|---------------|----------------|---------------------|
| Training Set    | 3037          | 605            | 2432                |
| Testing Set     | 1650          | 150            | 1500                |

## 4. Results

We evaluated models using 10-fold cross-validation. The SVM model achieved the highest mean accuracy of 0.93. Detailed accuracy results are as follows:

| Model           | Training Accuracy | Test Accuracy |
|-----------------|--------------------|---------------|
| Logistic Regression | 0.9338           | 0.9321        |
| Ridge Regression    | 0.9338           | 0.9321        |
| SVM                 | 0.9602           | 0.9412        |
| Random Forest       | 1.0000           | 0.9315        |
| Decision Tree       | 1.0000           | 0.8824        |

**Confusion Matrix for SVM:**

- True Negatives: 1428
- False Positives: 72
- False Negatives: 25
- True Positives: 125

![Confusion Matrix for SVM](path/to/confusion_matrix_svm.png)

### Insights

- Logistic Regression and Ridge Regression performed similarly, with stable accuracies.
- SVM outperformed all other models with the highest accuracy.
- Random Forest and Decision Tree had perfect training accuracies but lower test accuracies.

## 5. Conclusion

This project aimed to classify Near Earth Objects (NEOs) into hazardous or non-hazardous categories. Through various models, including SVM, which achieved the highest accuracy, we gained insights into asteroid classification and potential threats to Earth.

## 6. Resources

- [Code Repository](link/to/your/code)
