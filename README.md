# Aygaz Machine Learning Bootcamp  
**Kaggle Link:**  
[My Bootcamp Notebook](https://www.kaggle.com/code/nimetseyrek/mybootcampnotebook)  

## Movie Sentiment Analysis  
This project aims to perform sentiment analysis using a dataset of Turkish movie reviews. Both supervised and unsupervised learning algorithms were applied to analyze the data and evaluate model performance.

## Contents
- Data Loading and Preprocessing
- Exploratory Data Analysis (EDA)
- Supervised Learning Models
- Unsupervised Learning Models
- Model Selection and Hyperparameter Optimization
- Results
- Setup and Usage Instructions

## Dataset  
The project uses a CSV file named `turkish_movie_sentiment_dataset.csv`, containing movie names, reviews, and ratings. Missing values were cleaned, and ratings were normalized.

### Data Preprocessing  
- **Data Loading:** Loaded the CSV file and cleaned empty values in the `comment`, `film_name`, and `point` columns.  
- **Labeling:** Categorized reviews as `positive`, `neutral`, or `negative` based on ratings.  
- **Numerical Encoding:** Converted categorical columns (`film_name`, `sentiment`) into numerical values.  
- **Normalization:** Normalized the `point` column to a range between 0 and 1.  
- **Text Vectorization:** Converted comments into numerical form using TF-IDF.  
- **Dimensionality Reduction:** Reduced the dimensionality of the TF-IDF vectors using PCA.  
- **Feature Combination:** Combined TF-IDF vectors with numerical features for model training.

## Exploratory Data Analysis (EDA)  
To understand the fundamental characteristics of the dataset, I analyzed:

- Distribution of sentiment labels
- Distribution of normalized ratings
- Relationship between sentiment labels and normalized ratings

**Visualizations:**  
- A bar chart visualizing sentiment distribution  
- Histograms and KDE (Kernel Density Estimation) to show the distribution of ratings  
- Scatter plots showing the relationship between normalized ratings and sentiment

## Supervised Learning Models  
### Logistic Regression:  
- Trained and tested the model  
- **Performance Metrics:** Accuracy, Classification Report  
- Achieved high accuracy of **99.3%**.

### K-Nearest Neighbors (KNN):  
- Trained and tested the model  
- **Performance Metrics:** Accuracy, Classification Report  
- Lower accuracy of **71.6%**, underperforming compared to Logistic Regression.

## Unsupervised Learning Models  
### K-Means:  
- Applied clustering to the data  
- Calculated the silhouette score  
- Visualized clustering results  
- Achieved a silhouette score of **0.59**, indicating moderate cluster separation.

### DBSCAN:  
- Applied clustering to the data  
- Calculated the silhouette score  
- Visualized clustering results  
- Achieved a higher silhouette score of **0.88**, demonstrating strong cluster separation.

## Model Selection and Why Logistic Regression Performed Better  
### Dataset Characteristics  
The dataset consists of Turkish movie reviews and associated ratings, providing a structure well-suited to supervised learning algorithms. Key points include:

- **Sentiment Classification:** Reviews were labeled as `positive`, `neutral`, or `negative` based on ratings, enabling supervised learning algorithms to train on labeled data.  
- **Text Features:** Reviews were transformed into numerical features using techniques like TF-IDF, making them suitable for models like Logistic Regression.

### Why Logistic Regression Was the Best Performing Model  
1. **Linear Classification:**  
   Logistic Regression separates data points using a linear boundary, which is effective for datasets where features (e.g., TF-IDF) are linearly separable. In sentiment analysis, text features often have linear separability.

2. **Clear Class Differentiation:**  
   Logistic Regression is capable of creating clear distinctions between classes, which is essential when separating `positive`, `neutral`, and `negative` sentiments.

3. **Simplicity and Interpretability:**  
   The model’s internal structure is easy to understand and interpret. Logistic Regression provides transparent insights into how text features influence sentiment classification.

4. **Fast Training and Prediction:**  
   Logistic Regression trains and makes predictions quickly, making it ideal for larger datasets.

5. **Regularization to Prevent Overfitting:**  
   Logistic Regression includes regularization techniques to minimize overfitting, particularly useful when dealing with datasets with many features.

### Comparison with Other Supervised Models  
- **K-Nearest Neighbors (KNN):**  
   KNN is based on proximity, requiring more computation and often performing worse on high-dimensional data like TF-IDF vectors. The model slowed down and provided lower accuracy on this dataset.

- **Support Vector Machines (SVM) and Others:**  
   Although SVM and other complex models can achieve higher accuracy, they require more complex hyperparameter tuning and longer training times. Logistic Regression is a faster and simpler alternative, especially for this project.

## Results  
Logistic Regression was chosen as the best-performing supervised model, and after hyperparameter optimization, accuracy improved to **99.6%**. Among unsupervised models, DBSCAN demonstrated superior performance with a high silhouette score, indicating strong cluster separation.

## Setup and Usage Instructions
1. Install the necessary libraries:
   ```bash
   pip install pandas numpy scikit-learn seaborn matplotlib
2. Download the project files and place the turkish_movie_sentiment_dataset.csv file in the same directory as the data file.
3. Run the codes.

