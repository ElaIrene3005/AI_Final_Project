# Visitor Satisfaction Clustering using K-Means and PCA

This project applies **unsupervised learning** techniques to group survey respondents based on satisfaction-related responses. Using **K-Means Clustering** and **Principal Component Analysis (PCA)**, the goal is to identify meaningful clusters—such as "satisfied" vs. "not satisfied" visitors—without using predefined labels.

---

## Project Structure
```
├── data/
│ └── survey_data.csv # Cleaned numerical responses from Google Forms
├── clustering_analysis.ipynb # Jupyter Notebook containing the clustering and PCA code
└── README.md # Project documentation
```

---

## Objectives

- Apply **K-Means Clustering** to identify groups in the survey data
- Use **PCA** to reduce feature dimensions for better visualization
- Provide insights into patterns of visitor satisfaction

---

## Methodology

### 1. Preprocessing
- Only numerical responses from the Google Forms survey were used.
- Data was scaled (optional) and passed into the clustering algorithm.

### 2. K-Means Clustering
- Number of clusters: `2`
- Cluster labels were interpreted as:
  - `Cluster 0`: Not Satisfied
  - `Cluster 1`: Satisfied

### 3. PCA (Principal Component Analysis)
- Reduces high-dimensional features into 2 principal components.
- Enables easy visualization of cluster separation in 2D space.

### 4. Visualization
A scatter plot is generated using `matplotlib`:

- **Blue points** represent visitors labeled as **Not Satisfied**
- **Red points** represent visitors labeled as **Satisfied**

```python
plt.figure(figsize=(10, 7))
plt.scatter(df[df['Cluster'] == 0]['PC1'], df[df['Cluster'] == 0]['PC2'], c='blue', label='Cluster 1: Not Satisfied')
plt.scatter(df[df['Cluster'] == 1]['PC1'], df[df['Cluster'] == 1]['PC2'], c='red', label='Cluster 2: Satisfied')
plt.title('K-Means Clustering of Visitor Satisfaction')
plt.xlabel('Principal Component 1')
plt.ylabel('Principal Component 2')
plt.legend()
plt.show()
