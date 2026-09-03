---
layout: default
title: 'MIA Lab: Pre-processing'
---

# Pre-processing

## Why is this done?

Pre-processing in medical image analysis is essential for enhancing image quality, reducing artifacts, and standardizing images across different datasets. This step ensures that images are consistent and clear, which is crucial for accurate diagnosis and treatment planning. By removing noise and irrelevant background information, pre-processing prepares the images for advanced analysis techniques like segmentation and machine learning, ultimately leading to more reliable and precise outcomes.

Common pre-processing steps include:

- **Background removal**: focus on information-rich anatomical locations in the image.
- **Noise reduction**: removing unwanted noise within important locations to focus on useful content for the task.
- **Normalization**: adjusting the intensity values to a standard range across multiple images.
- **Resampling**: adjusting the image resolution to ensure consistency of algorithm performance.

## How is it done?

Pre-processing in medical image analysis typically involves several key steps:

- **Background removal**: in the specific case of brain imaging data, skull stripping (separating the brain from the skull and other surrounding structures) is typical in this category.
- **Denoising**: this is done using approaches like Gaussian blurring, median filtering, and more advanced methods like edge-aware or adaptive filtering.
- **Intensity normalization**: histogram matching is a common method to normalize information across an entire data-set.
- **Resampling**: this is done using linear, spline, and other forms of interpolation and quantization of data.

## Project ideas

Do combinations of pre-processing steps improve the performance additively? If there is an improvement with denoising, and separately, an improvement with normalization, does implementing both lead to a linear increase in improvements?

Are other more advanced methods of normalization (z-score normalization; z-score with 95% range) better than simple scaling between 0 and 1?

## Coding resources

- See `pymia.filtering.preprocessing`
- scikit-learn: [Pre-processing data](http://scikit-learn.org/stable/modules/preprocessing.html#preprocessing)
- [medpy.filter.IntensityRangeStandardization](http://loli.github.io/medpy/generated/medpy.filter.IntensityRangeStandardization.IntensityRangeStandardization.html)

## References

L. G. Nyúl, J. K. Udupa, and X. Zhang, New variants of a method of MRI scale standardization, IEEE Trans. Med. Imaging, vol. 19, no. 2, pp. 143-50, Feb. 2000.

J.-P. Bergeest and F. Jäger, A Comparison of Five Methods for Signal Intensity Standardization in MRI, in Bildverarbeitung für die Medizin 2008, Berlin Heidelberg: Springer, 2008, pp. 36-40.
