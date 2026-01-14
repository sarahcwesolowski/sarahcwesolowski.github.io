# Sarah Wesolowski - Personal Website

A clean, modern personal website built with pure HTML & CSS. No build tools required.

**Live site:** https://sarahcwesolowski.github.io

---

## Quick Start

1. Edit the HTML files directly
2. Preview locally by opening files in your browser
3. Push to GitHub to deploy

```bash
git add .
git commit -m "Your update message"
git push
```

GitHub Pages will automatically deploy your changes within a few minutes.

---

## Site Structure

```
├── index.html           # Homepage (About)
├── publications.html    # Academic publications
├── projects.html        # Projects listing
├── cv.html              # CV download page
├── 404.html             # Error page
├── css/
│   └── style.css        # All styles
├── projects/
│   └── project-template.html   # Template for new projects
└── assets/
    ├── img/             # Images (profile pic, project images)
    │   ├── prof_pic.jpg
    │   └── favicon.png
    └── pdf/             # PDFs
        └── Wesolowski_CV.pdf
```

---

## How to Update

### Update Your Bio

1. Open `index.html`
2. Find `<div class="about-content">`
3. Edit the text
4. Save and push

### Update Your Profile Photo

1. Replace `assets/img/prof_pic.jpg` with your new photo
2. Keep the same filename, or update the `<img>` tag in `index.html`

### Update Your CV

1. Replace `assets/pdf/Wesolowski_CV.pdf` with your new CV
2. Keep the same filename

### Add a Publication

1. Open `publications.html`
2. Find the year section (or add `<h2>YEAR</h2>` for a new year)
3. Copy this template and fill in your details:

```html
<div class="publication">
  <div class="publication-title">Paper Title</div>
  <div class="publication-authors">Author 1, Author 2, Your Name</div>
  <div class="publication-venue">Journal Name, Vol. X, Pages Y-Z (Year)</div>
  <div class="publication-links">
    <a href="https://paper-url.com" target="_blank" rel="noopener">
      <i class="fas fa-external-link-alt"></i> Paper
    </a>
    <a href="https://doi.org/your-doi" target="_blank" rel="noopener">
      <i class="fas fa-link"></i> DOI
    </a>
  </div>
</div>
```

### Add a Project

**Step 1:** Create the project page
1. Copy `projects/project-template.html` to a new file (e.g., `projects/my-project.html`)
2. Open and edit the TODOs in the template
3. Add your content

**Step 2:** Add it to the projects listing
1. Open `projects.html`
2. Remove the "Projects coming soon" placeholder
3. Add a project card:

```html
<article class="project-card">
  <a href="projects/my-project.html">
    <img src="assets/img/project-image.jpg" alt="Description">
  </a>
  <div class="project-card-content">
    <span class="project-category">Personal</span>
    <h3><a href="projects/my-project.html">Project Title</a></h3>
    <p>Brief description of the project.</p>
  </div>
</article>
```

### Update Social Links

Social links are in the footer of every HTML file. Search for `<div class="social-links">` and update the URLs.

---

## Design System

### Colors (edit in `css/style.css`)

| Color | Hex | Usage |
|-------|-----|-------|
| Hot Pink | `#ff00b4` | Primary accent |
| Cyan | `#00ffbc` | Secondary accent |
| Periwinkle | `#8ea5ff` | Tertiary accent |
| Lavender | `#c493ff` | Highlights |
| White | `#ffffff` | Backgrounds |
| Dark | `#1a1a2e` | Text |

### Fonts

- **Space Grotesk** - Headings
- **Inter** - Body text

Both are loaded from Google Fonts.

---

## Deployment

This site is hosted on **GitHub Pages**. Any push to the `main` branch will automatically deploy.

To deploy your changes:

```bash
# Check what's changed
git status

# Stage all changes
git add .

# Commit with a message
git commit -m "Update bio"

# Push to GitHub (deploys automatically)
git push
```

Your site will update within 1-2 minutes.

---

## Local Preview

Just open any HTML file directly in your browser:
- Double-click `index.html`, or
- Right-click → Open With → Your Browser

No server needed!

---

## Tips

- **Images:** Keep under 500KB for fast loading
- **Test mobile:** Resize your browser window or use DevTools (F12)
- **Backup:** Your site is version-controlled with Git, so you can always revert changes

---

## Files You Can Ignore

- `.nojekyll` - Tells GitHub Pages not to process with Jekyll
- `robots.txt` - Search engine instructions
- `LICENSE` - Open source license

---

## Need Help?

- [GitHub Pages Docs](https://docs.github.com/en/pages)
- [HTML Reference](https://developer.mozilla.org/en-US/docs/Web/HTML)
- [CSS Reference](https://developer.mozilla.org/en-US/docs/Web/CSS)
