# Sarah Wesolowski - Personal Website

**Live site:** https://sarahcwesolowski.github.io

---

## Site Structure

```
├── index.html           # Homepage (About)
├── publications.html    # Academic publications
├── cv.html              # CV page
├── 404.html             # Error page
├── css/style.css        # Styles
└── assets/
    ├── img/             # Images
    └── pdf/             # CV PDF
```

---

## How to Edit

### Update your bio
Edit `index.html` — find the `<div class="about-content">` section.

### Update your CV
1. Replace `assets/pdf/Wesolowski_CV.pdf` with your new PDF
2. Edit `cv.html` to update the summary shown on the page

### Add a publication
Edit `publications.html` — copy an existing `<div class="publication">` block:

```html
<div class="publication">
  <div class="publication-title">Paper Title</div>
  <div class="publication-authors">Authors</div>
  <div class="publication-venue">Journal, Vol. X (Year)</div>
  <div class="publication-links">
    <a href="URL" target="_blank" rel="noopener">
      <i class="fas fa-external-link-alt"></i> Paper
    </a>
  </div>
</div>
```

### Update profile photo
Replace `assets/img/prof_pic.jpg` with your new image.

### Update social links
Search for `<div class="social-links">` in each HTML file.

---

## Deploy Changes

```bash
git add .
git commit -m "Your message"
git push
```

Changes go live within 1-2 minutes.

---

## Preview Locally

Open any HTML file directly in your browser — no server needed.

---

## Colours

Edit `css/style.css` to change the colour palette:

```css
:root {
  --hot-pink: #ff00b4;
  --cyan: #00ffbc;
  --periwinkle: #8ea5ff;
  --lavender: #c493ff;
}
```
