---
layout: default
title: 'MIA Lab: Post-processing'
---

# Post-processing

## Why is this done?

Post-processing in medical image analysis is essential for refining and enhancing the results obtained from initial image processing and analysis. It involves artifact removal to improve segmentation quality and clarity. Additionally, post-processing can include the application of filters, morphological operations, and image fusion techniques to highlight specific features or regions of interest. This ensures that the final results are more accurate and interpretable, aiding medical professionals in making precise diagnoses and treatment decisions. Some common steps in this process include:

- **Smoothing**: reducing artifacts and noise in the segmented regions.
- **Morphological operations**: refining the shapes of segmented regions (e.g., dilation, erosion).
- **Validation**: comparing the results with ground truth data to assess accuracy.

## How is it done?

This step often involves algorithms such as:

- **Noise reduction**: apply filters to remove small, isolated regions or noise from the segmentation results.
- **Morphological operations**: use operations like dilation, erosion, opening, and closing to refine the shape and connectivity of segmented regions.
- **Smoothing**: implement techniques such as Gaussian smoothing to reduce jagged edges and create smoother boundaries.
- **Hole filling**: identify and fill small holes within segmented regions to ensure completeness.
- **Region merging**: combine adjacent regions that belong to the same anatomical structure but were segmented separately.
- **Contour correction**: adjust the boundaries of segmented regions to better match the actual anatomical structures.
- **Label correction**: manually or automatically correct mislabeled regions to improve accuracy.

## Project ideas

Can we leverage the segmentation performance by post-processing?

- Advanced morphological operators - opening, closing, top-hat, bottom-hat?
- Dense conditional random field (CRF) for improved segmentation.
- Would manual user interaction be justified (e.g., brushing) for time-effectiveness?

## Coding resources

- `mialab.filtering.postprocessing`, e.g. use `DenseCRF`

## References

P. Krähenbühl and V. Koltun, Efficient Inference in Fully Connected CRFs with Gaussian Edge Potentials, Advances in Neural Information Processing Systems, vol. 24, pp. 109-117, 2011.

S. Nowozin and C. H. Lampert, Structured Learning and Prediction in Computer Vision, Foundations and Trends in Computer Graphics and Vision, vol. 6, pp. 185-365, 2010.

P. Cattin, Image Segmentation, 2016. [Online] [https://www.miac.unibas.ch/SIP/pdf/SIP-07-Segmentation.pdf](https://www.miac.unibas.ch/SIP/pdf/SIP-07-Segmentation.pdf), see chapter 6 - Mathematical Morphology
