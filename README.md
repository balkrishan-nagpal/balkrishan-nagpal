# Acme Solutions — Welcome Page

A single-page, static website: a professional, responsive welcome page built
with plain HTML, CSS, and a small bit of JavaScript. No build step, no
frameworks — it works as-is on GitHub Pages, Netlify, or any static host.

## Structure

```
.
├── index.html             Page content and structure
├── css/
│   └── styles.css         All styling (design tokens are CSS variables at the top)
├── js/
│   └── script.js          Sets the footer's copyright year
├── images/
│   └── favicon.svg        Site icon
├── netlify.toml           Netlify build/publish + basic security headers
└── .gitignore
```

## Viewing it locally

No build tools needed. Either:

- Open `index.html` directly in a browser, or
- Serve it locally, e.g. `python3 -m http.server 8080` from this folder, then
  visit `http://localhost:8080`.

## Customizing the content

Everything is placeholder text for "Acme Solutions" — replace it with your
own copy:

- **Company name**: the `<span class="wordmark">` in the header, the `<title>`
  and `<meta name="description">` in `<head>`, and the footer line.
- **Headline & tagline**: inside `<section class="hero">`.
- **About section**: inside `<section class="about" id="about">`.
- **Services/features**: the three `<article class="feature">` blocks inside
  `<section class="features">`. Add, remove, or edit as needed.

## Customizing the look

All colors, fonts, and spacing are defined as CSS variables at the top of
`css/styles.css` under `:root`. Change a value there and it updates everywhere
it's used — for example `--color-primary` (navy) and `--color-accent`
(bronze) control the two main brand colors.

## Deploying to GitHub + Netlify

1. **Push to GitHub**
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/<your-username>/<your-repo>.git
   git push -u origin main
   ```

2. **Deploy on Netlify**
   - Log in to [Netlify](https://app.netlify.com) and choose **Add new site →
     Import an existing project**.
   - Connect your GitHub account and select this repository.
   - Build settings: leave the build command blank and set the publish
     directory to `.` (this is already set in `netlify.toml`, so Netlify
     should pick it up automatically).
   - Click **Deploy site**. Netlify will give you a live URL, which you can
     later point a custom domain at from the site's Domain settings.

Every push to `main` will automatically redeploy the site.
