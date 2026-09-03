---
layout: default
title: 'MIA Lab: Pipeline'
---

# Pipeline

In a typical medical image analysis (MIA) process, several sequential algorithmic steps are undertaken, in what is called a pipeline. This can vary depending on the complexity of the data and the problem statement, and for the purposes of the project in this course, our pipeline has as input two magnetic resonance (MR) image slices (i.e., a T1-weighted (T1w) image slice and a T2-weighted (T2w) image slice) and a segmentation of the brain into constituent structures (see [clinical background](/topics/clinical-background/)).

The pipeline itself consists of the following steps, which we will go over through the duration of this laboratory:

- [Pre-processing](/topics/pipeline/pre-processing/), which aims at improving the image quality for our machine learning algorithm
- [Registration](/topics/pipeline/registration/), which aims at aligning the two MR images
- [Feature extraction](/topics/pipeline/feature-extraction/), which aims to extract meaningful features from the MR images for the subsequent classification
- [Classification](/topics/pipeline/classification/), which performs a voxel-wise tissue classification using the extracted features
- [Post-processing](/topics/pipeline/post-processing/), which aims to improve the classification

The dashed boxes indicate pre-steps or selections that influence a step. The provided experiments (see [pre-processing](/topics/pipeline/pre-processing/) and others) correspond to boxes in the figure. Additionally, we will also have a look at the [evaluation](/topics/pipeline/evaluation/) of such a pipeline.

<figure>
  <img src="/images/pipeline.png" alt="The MIA Lab pipeline, from pre-processing to evaluation" />
</figure>

An in-depth description of the pipeline with references for further reading can be found in [1].

## References

[1] Pereira, S., Pinto, A., Oliveira, J., Mendrik, A. M., Correia, J. H., Silva, C. A.: Automatic brain tissue segmentation in MR images using Random Forests and Conditional Random Fields. Journal of Neuroscience Methods 270, 111-123, (2016). [https://doi.org/10.1016/j.jneumeth.2016.06.017](https://doi.org/10.1016/j.jneumeth.2016.06.017)
