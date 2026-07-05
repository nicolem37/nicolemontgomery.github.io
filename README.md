# Nicole Montgomery — Personal Website

A personal website for Nicole Montgomery, Quality Assurance Analyst. Built with plain HTML, CSS, and JavaScript — no build tools, no frameworks, no dependencies beyond two Google Fonts.

## Structure

```
├── index.html
├── css/
│   └── styles.css
├── js/
│   └── script.js
├── assets/
│   ├── headshot.jpg
│   ├── Nicole-Montgomery-Resume.pdf
│   ├── Nicole-Montgomery-Master-Career-Portfolio.pdf
│   └── artifacts/              (screenshot thumbnails used in the QA Portfolio gallery)
│       ├── sprint-documentation.jpg
│       ├── test-plan.jpg
│       ├── manual-test-cases.jpg
│       ├── test-execution-results.jpg
│       ├── requirement-traceability-matrix.jpg
│       ├── defect-reports.jpg
│       ├── api-test-collection.jpg
│       └── sql-validation.jpg
└── README.md
```

## Deploying to GitHub Pages

1. Create a new repository on GitHub (e.g. `nicolemontgomery.github.io` for a root user site, or any name for a project site).
2. Push these files to the repository's default branch:
   ```bash
   git init
   git add .
   git commit -m "Initial site"
   git branch -M main
   git remote add origin https://github.com/<your-username>/<repo-name>.git
   git push -u origin main
   ```
3. In the repository, go to **Settings → Pages**.
4. Under **Build and deployment**, set **Source** to "Deploy from a branch," pick the `main` branch and `/ (root)` folder, then save.
5. GitHub will publish the site at `https://<your-username>.github.io/<repo-name>/` (or `https://<your-username>.github.io/` if the repo is named `<your-username>.github.io`).

## One thing to check before publishing

The Contact section still has a **GitHub card with a placeholder link** (`github.com/nicolemontgomery`, pointing nowhere). Since this is a QA-focused site rather than a developer portfolio, you may want to either:
- Replace it with a real GitHub URL if you have one, or
- Remove that card entirely from the `.contact-grid` in `index.html` (it's the third `<a class="contact-card">` block, right after the LinkedIn one) and adjust `.contact-grid`'s CSS grid to 2 columns instead of 3.

Everything else — LinkedIn, email, all PDF links, all artifact-gallery page anchors — points to real, working destinations.

Also update `<link rel="canonical">` and the Open Graph tags in `<head>` with your live URL once you know it.

## Keeping content current

- **Résumé / Portfolio PDFs**: swap the files in `assets/` any time you have updated versions — keep the same filenames and the download links keep working automatically.
- **Artifact thumbnails**: the 8 images in `assets/artifacts/` were cropped from screenshots embedded in the Master Career Portfolio PDF. If you update the portfolio with new or different artifacts, replace the corresponding JPG (same filename) and double-check the `#page=N` anchor in that artifact card's link in `index.html` still points to the right page.

## Notes

- Typefaces: **Fraunces** (headlines, pull-quotes) and **Inter** (everything else), loaded from Google Fonts via CDN — both will fail to load only in environments without internet access; GitHub Pages has no issue with this.
- No build step. No JavaScript framework. No CSS framework. Just three files plus assets — this is intentional and keeps the site fast and easy to maintain by hand.
- Scroll-reveal animations are progressive enhancement only: the site is fully readable with JavaScript disabled, and animations are automatically skipped for users with `prefers-reduced-motion` enabled.
