# Personal Website — Edit Guide

Live site: https://kang99841-mini.github.io/personal_website/

Everything is in one file: **`index.html`**. Open it in any text editor (VS Code recommended). Each section is clearly labelled with a comment like `<!-- HERO -->` or `<!-- WORK -->` so you can jump straight to what you need.

---

## File & Folder Structure

```
personal_website/
├── index.html          ← The entire website (edit this)
├── icon/
│   ├── bytedance.png   ← ByteDance logo
│   ├── tencent.png     ← Tencent logo
│   └── NUS.jpg         ← NUS logo
└── resume/
    └── Chen_Kang_Resume_2025.pdf  ← Linked from the site
```

---

## How to Deploy Changes

After editing `index.html`, run these two commands in Terminal from the `personal_website` folder:

```bash
git add -A
git commit -m "describe what you changed"
git push
```

GitHub Pages will rebuild automatically. Changes are live within ~1 minute.

---

## Section-by-Section Edit Guide

### 1. Name, Title & Contact Details

Search for `<!-- NAV -->`. The nav shows your name and the "Let's Talk" email link.

```html
<span class="nav-name">Chen Kang</span>
```
```html
<a href="mailto:chenkang2124@gmail.com" class="nav-cta">Let's Talk</a>
```

The same email and phone appear in the `<!-- CTA -->` section at the bottom — update both places if your contact details change.

---

### 2. Hero — Headline & Intro Text

Search for `<!-- HERO -->`.

```html
<h1>
  Data pipelines that<br>
  <span class="accent">scale and hold up.</span>
</h1>

<p class="hero-sub">
  Data Engineer with production experience at Tencent and ByteDance. ...
</p>
```

Edit the `<h1>` for your headline and the `<p class="hero-sub">` for the one-paragraph intro.

---

### 3. Hero Stats Bar (the 4 numbers)

Search for `hero-stats`. Edit the value and label in each block:

```html
<div class="hstat">
  <div class="hstat-val">300M+</div>       ← the number
  <div class="hstat-label">Rows / Hour</div> ← the label below it
</div>
```

There are 4 of these blocks. Add or remove blocks as needed — the grid adjusts automatically.

---

### 4. Companies Strip (logos row under hero)

Search for `<!-- COMPANIES STRIP -->`. Each logo entry looks like:

```html
<div class="co-logo">
  <img src="icon/bytedance.png" alt="ByteDance" class="co-logo-img">
  <div>
    <div class="co-name">ByteDance</div>
    <div class="co-sub">Current · Data Engineer</div>
  </div>
</div>
```

**To add a new company:** Copy the block above, paste it after the last `</div>` before `</div class="companies-logos">`, update the image path, name, and subtitle.

**To add a logo image:** Drop the PNG/JPG file into the `icon/` folder and reference it as `src="icon/yourfile.png"`.

---

### 5. "What I Bring" Cards

Search for `<!-- WHAT I BRING -->`. Each card:

```html
<div class="prop-card">
  <div class="prop-icon">⚡</div>                ← emoji icon
  <div class="prop-title">Scale-first thinking</div>
  <p class="prop-body">Every pipeline I design...</p>
</div>
```

There are 3 cards in a row. Adding a 4th will wrap to a second row automatically.

---

### 6. Work Experience Cards

Search for `<!-- WORK -->`. Each job is a `work-card` block. Here is the full template:

```html
<div class="work-card reveal">
  <div class="wc-header">
    <img src="icon/YOURLOGO.png" alt="Company Name" class="wc-logo">
    <div>
      <div class="wc-role">Job Title</div>
      <div class="wc-company">Company Name</div>
    </div>
    <div class="wc-right">
      <div class="wc-date">Jan 2025 – Present</div>
      <!-- Remove the badge below if not current role -->
      <div class="wc-badge"><span class="wc-badge-dot"></span>Current</div>
    </div>
  </div>
  <div class="wc-divider"></div>
  <div class="wc-body">
    <div class="impact-grid">

      <!-- Each impact item: metric on top, description below -->
      <div class="impact-item">
        <div class="impact-num">YOUR METRIC</div>
        <div class="impact-desc">What that metric means in plain English</div>
      </div>

      <!-- Add more impact-item blocks as needed -->

    </div>
    <div class="tech-row">
      <span class="chip">Tech 1</span>
      <span class="chip">Tech 2</span>
      <span class="chip dim">Supporting Tech</span>  <!-- dim = lighter style -->
    </div>
  </div>
</div>
```

**To add a new role:** Paste this template inside the `<div class="work-grid">` block, before the closing `</div>`. Fill in your details. The newest role should sit at the top.

**To remove a role:** Delete the entire `<div class="work-card reveal"> ... </div>` block for that job.

---

### 7. Skills

Search for `<!-- SKILLS -->`. Each category is a `skill-card`:

```html
<div class="skill-card">
  <div class="skill-cat">Category Name</div>
  <div class="skill-tags">
    <span class="stag">Skill A</span>
    <span class="stag">Skill B</span>
  </div>
</div>
```

**To add a skill:** Add a `<span class="stag">New Skill</span>` inside the relevant `skill-tags` div.

**To add a new category:** Copy a `skill-card` block and paste it inside the `<div class="skills-grid">`. The grid fills columns automatically.

---

### 8. Education

Search for `<!-- EDUCATION -->`. Edit the degree, school name, and achievement list items:

```html
<div class="edu-deg">B.Sc. Business Analytics, Machine Learning</div>
<div class="edu-school">National University of Singapore</div>
<div class="edu-grade">🏅 Honours (Distinction)</div>
<div class="edu-achv">
  <div class="edu-achv-item">NUS School of Computing Dean's List</div>
  <!-- Add more lines here -->
</div>
```

**To add an achievement:** Add `<div class="edu-achv-item">Your achievement</div>` inside the `edu-achv` div.

---

### 9. Resume PDF

Replace `resume/Chen_Kang_Resume_2025.pdf` with your new file, then update the filename in `index.html`. Search for `Chen_Kang_Resume_2025.pdf` — it appears in 3 places (hero, CTA section, nav area).

---

## Quick Reference — CSS Colour Variables

If you ever want to tweak the colour theme, all colours are defined at the top of `index.html` inside the `<style>` block:

```css
:root {
  --blue-600: #1d4ed8;   ← primary blue (buttons, links, numbers)
  --blue-500: #2563eb;   ← secondary blue (company names, eyebrows)
  --text:     #111827;   ← main body text
  --text-2:   #4b5e7a;   ← secondary/muted text
  --bg:       #f5f7fa;   ← page background
  --border:   #e3e8f0;   ← card borders
}
```
