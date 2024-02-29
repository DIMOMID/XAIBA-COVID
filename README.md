# XAIBA-COVID: Explainable AI-Based Boosting for COVID-19 Detection from Chest X-Ray Images

## Brief Introduction

The COVID-19 pandemic has severely strained global healthcare systems, highlighting the need for quick and accurate diagnostic methods. Interpreting chest X-ray (CXR) images for COVID-19 detection, especially when differentiating from conditions like pneumonia, is complex due to overlapping symptoms.

XAIBA-COVID addresses the diagnostic challenge by employing an explainable AI-based boosting method to meticulously extract and analyze both local radiomic features from patchified Region of Interest (ROI) and global radiomic features from the entire ROI in CXR images. This dual approach facilitates nuanced differentiation among Normal, COVID-19, and Pneumonia cases, enhancing the model's diagnostic precision. By leveraging advanced algorithms for feature selection, XAIBA-COVID focuses on the most informative features, enhancing the efficacy of the ensemble classifiers—CatBoost, XGBoost, and LightGBM—in making accurate classifications. The integration of the Shapley Additive Explanations (SHAP) module ensures the model's interpretability, providing radiologists with a transparent and understandable basis for decision-making, thereby bridging the gap between advanced AI diagnostics and clinical application.
This GitHub repository presents XAIBA-COVID, showcasing its efficiency in using limited data for impactful clinical insights, and contributing to the rapid triage of COVID-19 cases in resource-constrained environments.


![PR_Flowchart_R3](https://github.com/DIMOMID/XAIBA-COVID/assets/96596774/2a6d016c-3321-4c70-97c0-c33f4407fa78)

## Radiomic Feature Groups

### Table 1: Extracted PyRadiomics Features, Grouped by Feature Category

| Feature Group | PyRadiomics Features List |
|---------------|---------------------------|
| **First-Order (18)** | 10 Percentile, 90 Percentile, Energy, Entropy, Interquartile Range, Kurtosis, Maximum, Mean Absolute Deviation, Mean, Median, Minimum, Range, Robust Mean Absolute Deviation, Root Mean Squared, Skewness, Total Energy, Uniformity, Variance |
| **Shape (14)** | Elongation, Flatness, Least Axis Length, Major Axis Length, Maximum 2D Diameter Column, Maximum2D Diameter Row, Maximum 2D Diameter Slice, Maximum 3D Diameter, Mesh Volume, Minor Axis Length, Sphericity, Surface Area, Surface Volume Ratio, Voxel Volume |
| **GLCM (24)** | Autocorrelation, Cluster Prominence, Cluster Shade, Cluster Tendency, Contrast, Correlation, Difference Average, Difference Entropy, Difference Variance, Id, Idm, Idmn, Idn, Imc1, Imc2, Inverse Variance, Joint Average, Joint Energy, Joint Entropy, MCC, Maximum Probability, Sum Average, Sum Entropy, Sum Squares |
| **GLDM (14)** | Dependence Entropy, Dependence Non Uniformity, Dependence Non Uniformity Normalized, Dependence Variance, Gray Level Non Uniformity, Gray Level Variance, High Gray Level Emphasis, Large Dependence Emphasis, Large Dependence High Gray Level Emphasis, Large Dependence Low Gray Level Emphasis, Low Gray Level Emphasis, Small Dependence Emphasis, Small Dependence High Gray Level Emphasis, Small Dependence Low Gray Level Emphasis |
| **GLRLM (16)** | Gray Level Non Uniformity, Gray Level Non Uniformity Normalized, Gray Level Variance, High Gray Level Run Emphasis, Long Run Emphasis, Long Run High Gray Level Emphasis, Long Run Low Gray Level Emphasis, Low Gray Level Run Emphasis, Run Entropy, Run Length Non Uniformity, Run Length Non Uniformity Normalized, Run Percentage, Run Variance, Short Run Emphasis, Short Run High Gray Level Emphasis, Short Run Low Gray Level Emphasis |
| **GLSZM (16)** | Gray Level Non Uniformity, Gray Level Non Uniformity Normalized, Gray Level Variance, High Gray Level Zone Emphasis, Large Area Emphasis, Large Area High Gray Level Emphasis, Large Area Low Gray Level Emphasis, Low Gray Level Zone Emphasis, Size Zone Non Uniformity, Size Zone Non Uniformity Normalized, Small Area Emphasis, Small Area High Gray Level Emphasis, Small Area Low Gray Level Emphasis, Zone Entropy, Zone Percentage, Zone Variance |
| **NGTDM (5)** | Busyness, Coarseness, Complexity, Contrast, Strength |


## Results and Performance

XAIBA-COVID demonstrates superior performance across various metrics, significantly outperforming existing AI methods in COVID-19 detection. Detailed results and comparisons are presented in the tables within the full paper.

### Table 3: XAIBA-COVID Performance for All Classes per Different Classifier Modules

| XAIBA-COVID Classifier Module | Class     | Precision (%) | Recall (%) | F1-Score (%) |
|-------------------------------|-----------|---------------|------------|--------------|
| CatBoost                      | Normal    | 92            | 87         | 89           |
|                               | Pneumonia | 94            | 97         | 96           |
|                               | COVID-19  | 93            | 91         | 92           |
| XGBoost                       | Normal    | 94            | 88         | 91           |
|                               | Pneumonia | 95            | 98         | 96           |
|                               | COVID-19  | 98            | 91         | 94           |
| LightGBM                      | Normal    | 95            | 90         | 93           |
|                               | Pneumonia | 96            | 98         | 97           |
|                               | COVID-19  | 96            | 95         | 95           |

### Table 4: Comparison of the Proposed XAIBA-COVID with Other AI Methods in COVID-19 Detection Based on CXR

| Authors                    | Approaches                                            | Accuracy (%) |
|----------------------------|-------------------------------------------------------|--------------|
| Horry et. al               | VGG19                                                 | 83.00        |
| Wehbe et. al               | DeepCOVID-XR (Ensemble CNNs)                          | 83.00        |
| Hertel et. al              | Majority Voting Deep Ensemble Model                   | 84.00        |
| Zhao et al.                | SC2Net (ResNet-18 & Spatial Attention Module)         | 84.23        |
| Tsiknakis et. al           | Inception V3                                          | 85.00        |
| Loey et. al                | Alexnet                                               | 85.20        |
| Nasiri et. al              | DenseNet169 + XGBoost                                 | 89.70        |
| Ozturk et. al              | DarkCovidNet                                          | 87.02        |
| Kymar et. al               | Resnet1523 + XGBoost                                  | 90.00        |
| Mahmud et. al              | CovXNet (CNN with Depthwise dilated convolution Inception V3) | 90.20 |
| Keidar et. al              | Ensemble DNNs Model                                   | 90.30        |
| Afifi et. al               | DenseNet161 with global and local attention-based features | 91.20 |
| Al-Timemy et. al           | ResNet-50+ ESD (Ensemble Subspace Discriminant)       | 91.60        |
| Rahimzade et. al           | Concatenation of Xception + ResNet50 V2               | 91.40        |
| Balasubramaniam et. al     | Ensemble + SAKHO (Self Adaptive Kill Herd Optimization) | 92.13 |
| Apostolopoulos et. al      | Inception RestNetV2                                   | 92.85        |
| Wang                       | COVID-Net                                             | 93.30        |
| **Proposed Model (CatBoost)**  | **XAIBA-COVID**                                           | **93.30**        |
| Shi et. al                 | Teacher Student Deformable Attention Module (DAM)     | 93.44        |
| Luz et. al                 | EfficientNet-B0-B5 with 4 blocks added                | 93.90        |
| Jiang et. al               | Swin Transformer and transformer in transformer       | 94.75        |
| Chaudhary et. al           | Efficient-CovidNet (EfficientNet-B1)                  | 95.00        |
| **Proposed Model (XGBoost)**   | **XAIBA-COVID**                                           | **95.30**        |
| **Proposed Model (LGMBoost)**  | **XAIBA-COVID**                                           | **95.77**        |

## Author Information

- **Name:** Omid Almasi
- **Email:** oalmasi@scu.edu
- **LinkedIn:** [www.linkedin.com/in/omid-almasi](www.linkedin.com/in/omid-almasi)

## Code Availability

The XAIBA-COVID code is openly available for public use. Feel free to use it for COVID-19 detection and related research.

## Citation

If XAIBA-COVID aids your research or clinical practice, please cite our work to support further advancements in COVID-19 diagnostics through AI and machine learning.

