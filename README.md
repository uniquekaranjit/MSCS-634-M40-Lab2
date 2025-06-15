# MSCS_634_Lab_2: K-Nearest Neighbors (KNN) vs Radius Neighbors (RNN) on Wine Dataset

## Purpose

The purpose of this lab was to explore and compare the performance of two instance-based classifiers—K-Nearest Neighbors (KNN) and Radius Neighbors (RNN)—using the Wine Dataset from the `sklearn` library. By experimenting with different parameter values (k for KNN and radius for RNN), the goal was to understand how these parameters influence classification accuracy and to determine which model performs better on this dataset.

---

## Key Insights and Observations

- **KNN Performance:**  
  The KNN classifier consistently achieved high accuracy, ranging from approximately 94.4% to 97.2%. The highest accuracy was observed at **k=15**, indicating that considering a moderate number of neighbors improves generalization.

- **RNN Performance:**  
  The RNN classifier, using large radius values (350 to 600) as specified in the lab instructions on unscaled data, showed significantly lower accuracy (~38.9%) across all radius values tested. This suggests that the chosen radii were not suitable to capture meaningful neighborhood structures in the data.

- **Model Comparison:**  
  KNN outperformed RNN by a large margin. The large radius values for RNN led to ambiguous neighborhood definitions and frequent assignment of outlier labels, reducing classification effectiveness. In contrast, KNN’s parameter tuning and use of scaled features contributed to its strong performance.

- **When to Use Which:**  
  KNN is preferable for this dataset and similar problems, especially with proper feature scaling and tuning of k. RNN could be useful in scenarios with varying data density or when the radius parameter can be carefully optimized based on domain knowledge.

---

## Challenges and Decisions

- **Scaling Considerations:**  
  Since RNN uses distance-based neighborhood within a radius, feature scaling is crucial. However, to follow the lab instructions exactly, RNN was implemented on unscaled data with large radius values, which likely contributed to its poor accuracy.

- **Parameter Selection:**  
  Choosing appropriate radius values for RNN was challenging due to the wide range and scale of features. The large radius values recommended by the lab did not align well with the natural feature distances after scaling, so the decision was made to run RNN on unscaled data as instructed.

- **Handling Outliers in RNN:**  
  The `outlier_label` parameter was set to handle points with no neighbors inside the radius. This may have impacted accuracy if outliers were misclassified.

- **Balancing Fair Comparison:**  
  KNN was applied with scaled features to ensure meaningful distance computation, while RNN used unscaled data per instructions. This difference should be considered when interpreting results.

---

This lab provided practical insights into the strengths and limitations of neighborhood-based classifiers and the importance of parameter tuning and feature scaling in achieving optimal performance.
