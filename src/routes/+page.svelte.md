---
layout: default
---

<script>
  import Calendar from "$lib/Calendar.svelte";
  import Instructor from "$lib/Instructor.svelte";
  import { class_data } from "$lib/classData";
  import { slack, github } from "$lib/constants";
</script>

# Medical Image Analysis Lab

Welcome to the Medical Image Analysis (MIA) Laboratory at the University of Bern, ARTORG Center for Biomedical Engineering Research.

## Course Overview

During the MIA Lab, you will work on the task of **brain tissue segmentation** from magnetic resonance (MR) images. You will implement and investigate a complete image analysis pipeline, including:

- **Pre-processing**: Image normalization and intensity correction
- **Registration**: Aligning images to a common reference space
- **Feature extraction**: Computing informative features from images
- **Voxel-wise tissue classification**: Machine learning for tissue segmentation
- **Post-processing**: Refinement of segmentation results
- **Evaluation**: Quantitative assessment of performance

Throughout the laboratory, you will learn and use various libraries and software tools essential in the medical image analysis domain, while working on a real-world biomedical engineering challenge.

## Schedule

The course runs from **September 2025 to January 2026** with lectures and lab sessions on **Wednesdays**.

<Calendar />

## Instructors

<div class="instructor-container">
  {#each class_data.instructors as instructor}
    <Instructor {instructor} />
  {/each}
</div>

## Learning Objectives

By the end of this course, you will be able to:

- Understand the fundamental concepts and challenges in medical image analysis
- Implement a complete image processing and analysis pipeline
- Apply machine learning techniques to medical imaging problems
- Evaluate and compare different approaches quantitatively
- Work with standard medical imaging file formats and tools
- Document and present your work in a scientific format

## Assessment

The course is assessed through:

- **Homework exercises** (3 exercises): Practice with image basics, pipeline implementation, and random forests
- **Mid-term presentation** (20%): Present your project progress and methodology
- **Final presentation** (30%): Present your complete project with results
- **Final report** (50%): Conference paper formatted report

## Resources

- **Course materials**: [GitBook documentation](https://ubern-mialab.gitbook.io/course/)
- **Code repository**: Available through the course
- **Contact**: Reach out to the instructors via email or during office hours

## Course Philosophy

This course features a **front-loaded teaching structure** where the fundamental concepts and techniques are taught in the first weeks, followed by an extended project period where you apply these concepts to solve a real medical imaging challenge. You'll work in groups and receive regular feedback from instructors.

---

*This course is part of the Masters program in Biomedical Engineering at the University of Bern.*
