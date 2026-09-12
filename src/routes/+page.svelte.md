---
layout: default
title: 'MIA Lab: Medical Image Analysis Laboratory'
---

<script>
  import Calendar from "$lib/Calendar.svelte";
  import Instructor from "$lib/Instructor.svelte";
  import { class_data, fixupLink } from "$lib/classData";
  import { github, code, artorg } from "$lib/constants";
</script>

# Medical Image Analysis Lab

Welcome to the Medical Image Analysis (MIA) Laboratory at the University of Bern, ARTORG Center for Biomedical Engineering Research.

## Course Overview

During the MIA Lab, you will work on the task of **brain tissue segmentation** from magnetic resonance (MR) images (see [data](/topics/data/)). You will implement and investigate a complete [image analysis pipeline](/topics/pipeline/), including:

- **[Pre-processing](/topics/pipeline/pre-processing/)**: image normalization and intensity correction
- **[Registration](/topics/pipeline/registration/)**: aligning images to a common reference space
- **[Feature extraction](/topics/pipeline/feature-extraction/)**: computing informative features from images
- **[Voxel-wise tissue classification](/topics/pipeline/classification/)**: machine learning for tissue segmentation
- **[Post-processing](/topics/pipeline/post-processing/)**: refinement of segmentation results
- **[Evaluation](/topics/pipeline/evaluation/)**: quantitative assessment of performance

Throughout the laboratory, you will learn and use [various libraries and software tools](/getting-started/tools/) essential in the medical image analysis domain, while working on a real-world biomedical engineering challenge, and investigate one of the elements of the pipeline in depth.

Enjoy!

## Schedule

The course runs from **September to December 2026** with lectures and lab sessions on **Wednesdays**. See the [detailed schedule](/getting-started/schedule/) for which pages go with which lecture.

<Calendar />

## Teaching Team

<div class="instructor-container">
  {#each class_data.instructors as instructor}
    <Instructor
      name={instructor.name}
      role={instructor.role}
      email={instructor.email}
      src={fixupLink(instructor.image)}
      officeHours={instructor.officeHours ?? []}
    />
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

- **[Coding exercises](/exercises/)**: practice with image basics, pipeline implementation, and random forests
- **Written multiple-choice exam** (40%): December 2, 2026
- **Final presentation** (60%): December 9 or December 16, 2026, with 10 minutes per group plus 2 minutes for questions

There will also be a formative **mid-term presentation** on November 11, 2026. Each group will have up to 5 minutes to present its approach, progress, challenges, and insights.

## Resources

- **[Getting started](/getting-started/)**: installation, tools, IDEs, the Ubelix HPC cluster, LaTeX, and visualization
- **[Topics](/topics/)**: clinical background, the data, and each step of the pipeline
- **[Exercises](/exercises/)**: the three homework exercises
- **Code repository**: <a href={code}>ubern-mialab/mialab</a>, and the rest of the code in the <a href={github}>ubern-mialab GitHub organization</a>
- **Contact**: reach out to the instructors via email or during office hours, [contact us on GitHub](https://github.com/orgs/ubern-mialab/people), or find us at the <a href={artorg}>MIA group at the ARTORG Center</a>

## Course Philosophy

This course features a **front-loaded teaching structure** where the fundamental concepts and techniques are taught in the first weeks, followed by an extended project period where you apply these concepts to solve a real medical imaging challenge. You'll work in groups and receive regular feedback from instructors.

---

*This course is part of the Masters program in Biomedical Engineering at the University of Bern.*
