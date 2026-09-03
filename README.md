# ubern-mialab.github.io

This is the homepage for the Medical Image Analysis (MIA) Laboratory course at University of Bern.

## About

The MIA Lab is a hands-on course where students work on brain tissue segmentation from MR images, implementing a complete medical image analysis pipeline including:

- Pre-processing
- Registration
- Feature extraction
- Voxel-wise tissue classification
- Post-processing
- Evaluation

## Website

This website is built using [SvelteKit](https://kit.svelte.dev/) and deployed via GitHub Pages. It provides:

- Course schedule and overview
- Topic pages covering the clinical background, the data, and every step of the pipeline
- Getting started guide: installation, tools, IDEs, the Ubelix HPC cluster, LaTeX, and visualization
- Exercise descriptions

All course content lives in this repository. It was previously hosted on GitBook
(`ubern-mialab.gitbook.io/course`), which has been retired in favour of these pages.

## Development

### Installation

```bash
npm install
```

### Development Server

```bash
npm run dev
```

Visit http://localhost:5173 to see the site.

### Building

```bash
npm run build
```

The built site will be in the `build/` directory.

### Preview Production Build

```bash
npm run preview
```

## Deployment

The site automatically deploys to GitHub Pages when changes are pushed to the `main` branch via GitHub Actions.

## Course Information

- **Institution**: University of Bern, ARTORG Center
- **Instructors**: Prof. Mauricio Reyes, Amith Kamath, Shelley Zixin Shu, Michael Mueller
- **Schedule**: Autumn 2025 (September 2025 - January 2026)
- **Code**: [ubern-mialab/mialab](https://github.com/ubern-mialab/mialab)

## Credits

This website design is based on the [ubern-image-analysis](https://github.com/ubern-image-analysis/ubern-image-analysis.github.io) course website template.
