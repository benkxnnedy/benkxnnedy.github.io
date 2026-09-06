# Ben Kennedy — Network Engineering Portfolio

Astro + Markdown portfolio focused on network engineering, automation, CCIE Enterprise Infrastructure and a future move into London financial-markets infrastructure.

## Why this version exists

Projects, Labs and CCIE Journal entries are now content-driven. You do **not** edit HTML to publish a post.

## Local setup

```bash
npm install
npm run dev
```

Open the local URL Astro prints (normally `http://localhost:4321`).

## Add a CCIE Journal post

Create a new file in:

```text
src/pages/ccie-journal/
```

For example:

```text
src/pages/ccie-journal/ospf-lsa-troubleshooting.md
```

Start it with:

```md
---
layout: ../../layouts/PostLayout.astro
title: "Troubleshooting OSPF LSA Behaviour"
summary: "What I observed, why it happened and how I verified it."
date: 2026-09-10
type: "CCIE Journal"
status: "Study note"
tags: ["OSPF", "LSA", "Troubleshooting"]
---

## Problem

Write the post here.
```

Commit and push. The Journal index automatically discovers the file and adds it.

## Add a lab

Create a Markdown file in `src/pages/labs/` using the same pattern. Use:

```md
layout: ../../layouts/PostLayout.astro
type: "Lab"
category: "Multicast"
```

## Add a project

Create a Markdown file in `src/pages/projects/`.

Projects support these extra fields:

```md
featured: true
order: 1
category: "Production automation"
```

`featured: true` allows the project to appear on the homepage. `order` controls ordering.

## Images

Put sanitized images in:

```text
public/images/projects/
public/images/labs/
public/images/ccie/
```

Then reference one from Markdown:

```md
![CML topology](/images/ccie/my-topology.png)
```

Never publish production hostnames, IP addressing, configs, credentials, internal screenshots or employer-sensitive topology.

## Edit normal pages

- Homepage: `src/pages/index.astro`
- About: `src/pages/about/index.astro`
- Skills: `src/pages/skills/index.astro`
- Contact: `src/pages/contact/index.astro`
- Global design: `src/styles/global.css`

## Build before pushing

```bash
npm run build
```

If the build succeeds, the generated static site is in `dist/`.

## Git + Vercel workflow

Recommended workflow:

```bash
git add .
git commit -m "Add multicast RPF lab"
git push
```

Connect the GitHub repository to Vercel once. Every push to the production branch then triggers a deployment automatically.

## Public-launch checklist

- Replace LinkedIn placeholder.
- Replace GitHub placeholder.
- Add a professional public email address.
- Review all wording for employer confidentiality.
- Add a custom domain if desired.

## Change your public details

Edit one file:

```text
src/data/site.js
```

Add your LinkedIn, GitHub and public email there. The Contact page updates automatically.

## Post templates

Copy one of these instead of starting from scratch:

```text
templates/ccie-post.md
templates/lab-post.md
templates/project-post.md
```

## Vercel settings for the existing project

Because the existing Vercel project was temporarily set to **Other** during the original static deployment, use these settings when this Astro repository replaces it:

```text
Framework preset: Astro (preferred) OR Other
Install command: npm install
Build command: npm run build
Output directory: dist
```

If you import the GitHub repository as a new Vercel project, Vercel should detect Astro from `package.json` automatically.
