
Unsupervised learning is a type of machine learning where algorithms learn patterns from unlabeled data.
Unlike supervised learning, there's no predefined output or target variable. The model is left to its own devices to discover hidden structures and relationships within the data.

## **Key Characteristics:**

- **Unlabeled Data:** The data used for training doesn't have specific labels or categories assigned to it.
- **Pattern Discovery:** The algorithm's primary goal is to identify patterns, clusters, or anomalies within the data.
- **Self-Organization:** The model learns to organize the data based on inherent similarities and differences.


## **Common Techniques:**

1. **Clustering:**
    
    - **K-Means Clustering:** Divides data into a specified number of clusters based on similarity.
    - **Hierarchical Clustering:** Creates a hierarchy of clusters, starting from individual data points and merging them into larger clusters.
    - **DBSCAN:** Groups together points that are closely packed together (core points) and marks outliers.
2. **Dimensionality Reduction:**
    
    - **Principal Component Analysis (PCA):** Reduces the dimensionality of data while preserving most of the variance.
    - **t-SNE:** Visualizes high-dimensional data in a lower-dimensional space, often 2D or 3D.
3. **Anomaly Detection:**
    
    - **Isolation Forest:** Identifies anomalies by isolating them in decision trees.
    - **One-Class SVM:** Defines a boundary around normal data points, classifying anything outside as an anomaly.

**Applications:**

- **Customer Segmentation:** Grouping customers based on their behavior and preferences.
- **Anomaly Detection:** Identifying fraudulent transactions or system failures.
- **Feature Engineering:** Creating new features from existing ones to improve model performance.
- **Image and Video Analysis:** Recognizing patterns in images and videos, such as facial recognition or object detection.
- **Natural Language Processing:** Topic modeling and text clustering.

**In essence, unsupervised learning empowers machines to learn from raw data, making it a powerful tool for extracting valuable insights and discovering hidden knowledge.**