---
layout: default
title: 'MIA Lab: Feature extraction'
---

# Feature extraction

## Why is this done?

Feature extraction in medical image analysis is crucial for transforming raw image data into meaningful information that can be used for diagnosis, classification, and prediction. Identifying and isolating relevant features enhances the accuracy and efficiency of subsequent tasks. These features can be:

- **Shape features**: describing the geometry of structures (e.g., area, perimeter, compactness).
- **Texture features**: analyzing the texture patterns within the image (e.g., contrast, entropy).
- **Intensity features**: measuring the intensity values within regions of interest.

## How is it done?

Feature extraction in medical image analysis involves several key steps and techniques. Here are some well researched methods:

- **Local Binary Patterns (LBP)**: captures texture features by comparing pixel intensities.
- **Gray-Level Co-occurrence Matrix (GLCM)**: analyzes spatial relationships between pixels to extract texture features.
- **Gray-Level Run-Length Matrix (GLRM)**: measures the length of consecutive pixels with the same intensity.
- **Completed Local Binary Patterns (CLBP)**: an extension of LBP that includes additional information about pixel intensity variations.
- **Feature fusion**: combining multiple features to improve the accuracy and robustness of the analysis.
- **Deep learning approaches**: utilizes neural networks to automatically learn and extract features from images.

## Project ideas

A typical optimization for faster processing is to check if we can reduce the number of features to decrease the model complexity and the computational burden. Some steps in this direction could include:

- Decision forest feature importance
- Principal component analysis (PCA)
- Mutual information based feature selection

Furthermore, what features could be used to improve our model?

- Investigate other features
  - Hemisphere feature
  - Filter banks
  - Histogram of oriented gradients (HOGs)
- 2-D / 3-D differences

## Coding resources

- [scikit-image](https://scikit-image.org/docs/dev/api/skimage.feature.html): feature module
- [scikit-learn](http://scikit-learn.org/stable/modules/decomposition.html#decompositions): dimensionality reduction
- [Parallelized mutual information](https://github.com/danielhomola/mifs) based feature selection

## References

H. Peng, F. Long, and C. Ding, Feature selection based on mutual information criteria of max-dependency, max-relevance, and min-redundancy, IEEE Transactions on Pattern Analysis and Machine Intelligence, vol. 27, no. 8, pp. 1226-38, 2005.
