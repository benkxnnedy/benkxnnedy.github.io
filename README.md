# Ben Kennedy — Network Engineering Portfolio

Astro + Markdown portfolio focused on network engineering, automation and a technical blog-style post feed.

## Local setup

```bash
npm install
npm run dev
```

Open the URL Astro prints, normally `http://localhost:4321`.

## Site structure

- Homepage: `src/pages/index.astro`
- About: `src/pages/about/index.astro`
- Posts: `src/pages/posts/`
- Contact: `src/pages/contact/index.astro`
- Global design: `src/styles/global.css`

Technical posts live in `src/pages/posts/` and use `type: "Post"` in their Markdown frontmatter.

## Add a post

Copy `templates/post.md` into `src/pages/posts/` and give it a descriptive filename such as:

```text
src/pages/posts/bgp-path-selection.md
```

Posts are sorted newest first to create a simple blog-style feed.

## Post frontmatter

Useful frontmatter fields include:

```yaml
type: "Post"
category: "Datacenter"
tags: ["BGP EVPN", "VXLAN"]
```

The two newest posts appear automatically on the homepage.

## Images

Put sanitized images in `public/images/` and reference them with a root-relative URL:

```md
![CML topology](/images/projects/my-topology.png)
```

Never publish production hostnames, addressing, configs, credentials, internal screenshots or employer-sensitive topology.

## Build before pushing

```bash
npm run build
```

The generated static site is written to `dist/`.

## Vercel settings

```text
Framework preset: Astro
Install command: npm install
Build command: npm run build
Output directory: dist
```
