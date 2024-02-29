# XAIBA-COVID: Explainable AI-Based Boosting for COVID-19 Detection from Chest X-Ray Images

## Brief Introduction

The COVID-19 pandemic continues to challenge global healthcare systems, underscoring the need for rapid and accurate diagnostic solutions. XAIBA-COVID emerges as a cutting-edge solution designed to enhance the diagnosis of COVID-19, pneumonia, and normal cases through chest X-ray (CXR) imaging. This research introduces an explainable AI-based boosting approach that extracts and analyzes a vast array of local and global radiomic features from the lung regions in CXR images. By employing advanced feature selection and classification techniques, XAIBA-COVID aims to significantly improve the accuracy and interpretability of COVID-19 diagnostics, offering a valuable tool for radiologists and healthcare professionals in managing the pandemic.

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

## Comparison with Other AI Methods

The proposed XAIBA-COVID model showcases remarkable accuracy, exceeding that of established models like VGG19, DeepCOVID-XR, and various ensemble DNN models, confirming its potential as a leading solution in COVID-19 CXR image analysis.

## Access and Use

For full implementation details and to access the code, please visit our GitHub page: [https://github.com/DIMOMID/XAIBA-COVID](https://github.com/DIMOMID/XAIBA-COVID).

## Citation

If XAIBA-COVID aids your research or clinical practice, please cite our work to support further advancements in COVID-19 diagnostics through AI and machine learning.

