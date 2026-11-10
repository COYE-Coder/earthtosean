# Portfolio Website Design: earthtosean.com

**Date**: 2026-03-13
**Status**: Approved
**Owner**: Sean Carter

---

## Overview

Redesign of earthtosean.com from Dorik-hosted single-page portfolio to a Jekyll-based static site hosted on GitHub Pages. Uses the al-folio academic theme with custom styling to reflect both professional (remote sensing scientist) and personal (music, birding, Vietnamese heritage) identities.

## Goals

1. Eliminate hosting costs (Dorik subscription → free GitHub Pages)
2. Transfer domain from GoDaddy to Cloudflare (~$10/year)
3. Create a personal hub that shows personality beyond just work
4. Support blogging with distinct science/personal categories
5. Auto-generate publications from BibTeX
6. Easy to maintain and update

## Site Structure

```
earthtosean.com/
├── Home (About)      ← Landing page with bio, photo, quick links
├── Projects          ← Research + personal projects
├── Blog              ← Science + Personal categories
├── Publications      ← Auto-generated from BibTeX
└── CV                ← PDF download + inline version
```

**Navigation**: Top nav bar with logo (blue robot) on left, links on right.
**Footer**: Social links (GitHub, LinkedIn, Google Scholar), email, location.

## Color Palettes

### Science Palette (earth → arctic → space)
| Role | Color | Hex |
|------|-------|-----|
| Primary | Warm earth brown | `#5D4E37` |
| Secondary | Arctic blue-grey | `#7BA3B5` |
| Accent | Deep space | `#1B2838` |
| Background | Clean white | `#FAFAFA` |

### Personal Palette (psychedelic twist)
| Role | Color | Hex |
|------|-------|-----|
| Primary | Dusty magenta | `#8B4A6B` |
| Secondary | Golden amber | `#E8A849` |
| Accent | Forest teal | `#3D6B5C` |

### Usage
- Science blog posts: arctic-blue tag chip
- Personal blog posts: amber/magenta tag chip
- Projects page: science palette
- About page: blends both palettes

### Typography
- Primary font: Inter or Source Sans Pro (clean, modern sans-serif)
- Code blocks: JetBrains Mono or Fira Code

## Page Details

### Home/About
- **Photo**: Vietnam candid photo (personality over polish)
- **Bio**: Remote sensing scientist at Leidos Earth Intelligence team, MS Systems Ecology
- **Highlights**: Current work (snow remote sensing) + personal interests teaser
- **Links**: GitHub, LinkedIn, Google Scholar, email prominently displayed

### Projects
- Card grid layout
- Each card: title, description, thumbnail, tags, links (GitHub, demo, blog post)
- Featured projects:
  - CropScope (annual cropland mapping)
  - Landscape Explorer (land-use change visualization)
  - Fire Detection (GEO-LEO imagery fusion)
  - Aquatic Invasive Species pipeline

### Blog
- Two-category system: "Science" | "Personal"
- Filter toggle or tabs at top
- Each post: title, date, category tag (color-coded), excerpt
- Syntax highlighting for code
- Science topics: remote sensing, GEE, deep learning, pangeo/STAC
- Personal topics: classical music, birding, Vietnamese culture

### Publications
- Auto-generated from `.bib` file using Jekyll Scholar
- Display: title, authors (with self highlighted), journal, year
- Links: PDF, DOI, GitHub repo if applicable
- Sorted by year descending

### CV
- Inline HTML version (scannable)
- PDF download button at top
- Sections: Experience, Education, Skills, Publications, Additional

## Technical Implementation

### Stack
- **Theme**: al-folio (Jekyll)
- **Hosting**: GitHub Pages (free)
- **Domain**: earthtosean.com (transfer GoDaddy → Cloudflare)
- **Build**: Jekyll + GitHub Actions

### Repository Structure
```
e2s_website/
├── _config.yml           ← Site configuration
├── _data/                 ← CV data, navigation
├── _bibliography/         ← BibTeX files
├── _posts/                ← Blog posts (markdown)
├── _projects/             ← Project pages
├── _pages/                ← About, CV, etc.
├── assets/
│   ├── img/              ← Photos, project thumbnails
│   ├── pdf/              ← CV PDF, paper PDFs
│   └── css/              ← Custom color overrides
├── CNAME                  ← earthtosean.com
└── docs/plans/            ← This design doc
```

### Customizations Needed
1. Color scheme override in `_sass/_variables.scss`
2. Blog category filtering (Science/Personal)
3. Category-specific tag styling
4. Logo integration (blue robot as favicon + header)

## Assets Available

| Asset | File | Use |
|-------|------|-----|
| Logo | `e2s_logo.png` | Favicon, header |
| Profile photo | `WhatsApp Image 2026-03-12...` | About page |
| Professional photo | `linkedin_pic.jpeg` | CV section (optional) |

## Content Checklist (Owner: Sean)

- [ ] Updated CV (PDF + structured text)
- [ ] BibTeX file with all publications
- [ ] Project descriptions (title, summary, links, thumbnail each)
- [ ] Bio text (2-3 paragraphs)
- [ ] Social links (GitHub, LinkedIn, Google Scholar URLs)
- [ ] Blog post drafts (if any)
- [ ] Updated skills list (include: Pangeo stack, STAC, Leidos work)

## Domain Transfer Steps

1. Unlock domain in GoDaddy
2. Get authorization/EPP code from GoDaddy
3. Create Cloudflare account, initiate transfer (~$10)
4. Confirm transfer via email
5. Wait 5-7 days for transfer
6. Configure DNS:
   - A records → GitHub Pages IPs
   - CNAME: www → username.github.io
7. Add CNAME file to repo

## Implementation Plan

1. Fork/clone al-folio theme
2. Configure `_config.yml` with site info
3. Add custom color variables
4. Set up blog category system
5. Add placeholder content for all sections
6. Configure GitHub Pages + CNAME
7. Test locally with `bundle exec jekyll serve`
8. Push to GitHub, verify deployment
9. Transfer domain (can happen in parallel)
10. Populate real content

---

## Appendix: Sean's Background

**Current Role**: Leidos, Earth Intelligence team (snow remote sensing)

**Previous**:
- Working Lands for Wildlife (cropland deep learning)
- OneConcern (supply chain resilience)
- BAERI/NASA (fire detection)
- NTSG (geospatial data science)

**Education**:
- MS Systems Ecology, University of Montana
- BA Organismal Biology, Colorado College (Piano minor)

**Technical Skills**:
- Machine Learning / Deep Learning (PyTorch, TensorFlow)
- Google Earth Engine
- Geospatial Python (Pangeo stack, STAC)
- Remote Sensing (MODIS, Landsat, Sentinel, GOES, SMAP)
- Cloud Computing (AWS)

**Personal Interests**:
- Classical piano
- Birding
- Vietnamese heritage/culture
