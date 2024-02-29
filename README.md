# XAIBA-COVID: Explainable AI-Based Boosting for COVID-19 Detection from Chest X-Ray Images

## Brief Introduction

The COVID-19 pandemic has severely strained global healthcare systems, highlighting the need for quick and accurate diagnostic methods. Interpreting chest X-ray (CXR) images for COVID-19 detection, especially when differentiating from conditions like pneumonia, is complex due to overlapping symptoms.

XAIBA-COVID addresses this challenge with an explainable AI-based boosting method to extract and analyze radiomic features from CXR images, enabling the distinction between Normal, COVID-19, and Pneumonia cases. This approach utilizes advanced algorithms to select the most informative features and employs ensemble classifiers like CatBoost, XGBoost, and LightGBM for accurate classification. The interpretability of the model is ensured through the Shapley Additive Explanations (SHAP) module, enhancing radiologists' decision-making capabilities.

This GitHub repository presents XAIBA-COVID, showcasing its efficiency in using limited data for impactful clinical insights, and contributing to the rapid triage of COVID-19 cases in resource-constrained environments.

![PR_Flowchart_R3](https://github.com/DIMOMID/XAIBA-COVID/assets/96596774/2a6d016c-3321-4c70-97c0-c33f4407fa78)

## Key Contributions

1. **Advanced Feature Extraction**: Introducing an advanced explainable AI-based boosting algorithm for comprehensive quantitative analysis of radiomic features from CXR images, focusing on the lung area as the Region of Interest (ROI).
2. **Enhanced Diagnostic Accuracy**: Addressing the challenge of false positives by distinguishing COVID-19 from similar respiratory conditions through a nuanced analysis of radiomic features.
3. **Optimized Ensemble Classifiers**: Incorporating a classification module with optimized ensemble classifiers (CatBoost, XGBoost, and LightGBM) to boost detection reliability.
4. **Interpretability and Transparency**: Utilizing the Shapley Additive Explanations (SHAP) module to provide insights into the decision-making process, enhancing the interpretability of AI-driven diagnostics.
5. **Comprehensive Evaluation**: Demonstrating the model's efficacy in clinical decision-making through extensive experiments, particularly valuable in resource-constrained settings.

## Radiomic Feature Groups

- **First-Order Features**: Including Energy, Entropy, Kurtosis, Skewness, and more.
- **Shape Features**: Assessing the geometry and size of the lung ROI.
- **Texture Features**: Analyzing patterns and variations within the lung area through GLCM, GLDM, GLRLM, GLSZM, and NGTDM.

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
| Proposed Model (CatBoost)  | XAIBA-COVID                                           | 93.30        |
| Shi et. al                 | Teacher Student Deformable Attention Module (DAM)     | 93.44        |
| Luz et. al                 | EfficientNet-B0-B5 with 4 blocks added                | 93.90        |
| Jiang et. al               | Swin Transformer and transformer in transformer       | 94.75        |
| Chaudhary et. al           | Efficient-CovidNet (EfficientNet-B1)                  | 95.00        |
| Proposed Model (XGBoost)   | XAIBA-COVID                                           | 95.30        |
| Proposed Model (LGMBoost)  | XAIBA-COVID                                           | 95.77        |

## Comparison with Other AI Methods

The proposed XAIBA-COVID model showcases remarkable accuracy, exceeding that of established models like VGG19, DeepCOVID-XR, and various ensemble DNN models, confirming its potential as a leading solution in COVID-19 CXR image analysis.

## Access and Use

For full implementation details and to access the code, please visit our GitHub page: [https://github.com/DIMOMID/XAIBA-COVID](https://github.com/DIMOMID/XAIBA-COVID).

## Citation

If XAIBA-COVID aids your research or clinical practice, please cite our work to support further advancements in COVID-19 diagnostics through AI and machine learning.

