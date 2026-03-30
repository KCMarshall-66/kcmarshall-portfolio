# kcmarshall.com — Portfolio

Personal portfolio for **KC Marshall**, Senior Principal UX Design Lead.
Built with semantic HTML + CSS. Deployed via Vercel. No frameworks, no dependencies.

---

## Folder Structure

```
kcmarshall-portfolio/
├── index.html                          ← Homepage
├── 404.html                            ← Custom 404 page
├── vercel.json                         ← Vercel routing + cache config
├── work/
│   ├── onetrust-design-system.html     ← Case Study 01 (live)
│   ├── schlage-ecommerce.html          ← Case Study 02 (add next)
│   ├── healthcare-service-design.html  ← Case Study 03 (add next)
│   └── perq-platform.html             ← Case Study 04 (add next)
└── assets/
    ├── images/
    │   ├── README.md                   ← Image naming guide
    │   ├── profile.jpg                 ← Your headshot (add this first!)
    │   ├── thumb-onetrust.jpg          ← Homepage work card thumbnail
    │   ├── thumb-schlage.jpg
    │   ├── thumb-healthcare.jpg
    │   ├── thumb-perq.jpg
    │   └── onetrust/                   ← Case study artifact images
    │       ├── audit-matrix.jpg
    │       ├── pendo-analysis.jpg
    │       └── ...
    └── resume/
        └── Kevin-Marshall-2026-Resume.pdf
```

---

## 🚀 Deploying to Vercel (Step-by-Step)

### Step 1 — Create a GitHub repository

1. Go to [github.com](https://github.com) → click **New repository**
2. Name it `kcmarshall-portfolio` (or similar)
3. Set it to **Private** (you can make it public later)
4. Do **not** initialize with a README (you already have one)
5. Click **Create repository**

### Step 2 — Push this folder to GitHub

Open Terminal, navigate to this folder, then run:

```bash
cd "path/to/kcmarshall-portfolio"   # adjust to your actual path
git init
git add .
git commit -m "Initial portfolio launch"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/kcmarshall-portfolio.git
git push -u origin main
```

### Step 3 — Connect to Vercel

1. Go to [vercel.com](https://vercel.com) → **Sign up with GitHub** (free)
2. Click **Add New Project**
3. Select your `kcmarshall-portfolio` repo → click **Import**
4. Framework Preset: **Other** (leave all settings as default)
5. Click **Deploy** — Vercel builds and gives you a live `.vercel.app` URL in ~30 seconds

### Step 4 — Connect your domain (kcmarshall.com)

1. In Vercel dashboard → your project → **Settings → Domains**
2. Add `kcmarshall.com` and `www.kcmarshall.com`
3. Vercel gives you DNS records — log into your domain registrar and add them:
   - Type `A`, Name `@`, Value `76.76.21.21`
   - Type `CNAME`, Name `www`, Value `cname.vercel-dns.com`
4. DNS propagation takes 5–30 minutes. Then you're live!

---

## ✏️ Adding Content (Images)

### Quickest way to add your headshot and project thumbnails:

1. Export images from Figma at **2x** resolution
2. Compress at [squoosh.app](https://squoosh.app) (JPG, quality 85)
3. Drop into the correct folder in `assets/images/` (see `README.md` inside that folder)
4. Update the `src` attributes in the relevant HTML files
5. Commit and push — Vercel auto-deploys in seconds

### Where to add images in the HTML:

**Profile photo** (`index.html` ~line 703):
```html
<!-- Replace this: -->
<div class="about-photo">Photo</div>

<!-- With this: -->
<div class="about-photo">
  <img src="/assets/images/profile.jpg" alt="KC Marshall" style="width:100%;height:100%;object-fit:cover;border-radius:50%" />
</div>
```

**Work card thumbnails** (`index.html` — each `.work-thumb` div):
```html
<!-- Replace the CSS gradient background with a real image: -->
<div class="work-thumb wt-onetrust">
  <img src="/assets/images/thumb-onetrust.jpg" alt="OneTrust Design System"
       style="width:100%;height:100%;object-fit:cover;position:absolute;inset:0;opacity:0.7" />
  ...
</div>
```

**Case study artifact images** (`work/onetrust-design-system.html` — each `.artifact-img` div):
```html
<!-- Replace placeholder: -->
<div class="artifact-img ai-dark">Component Audit Matrix</div>

<!-- With real image: -->
<div class="artifact-img ai-dark" style="padding:0;overflow:hidden">
  <img src="/assets/images/onetrust/audit-matrix.jpg" alt="Component Audit Matrix"
       style="width:100%;height:100%;object-fit:cover" />
</div>
```

---

## 📄 Adding a New Case Study

1. Duplicate `work/onetrust-design-system.html`
2. Rename it (e.g. `work/schlage-ecommerce.html`)
3. Update the content — follow the same 6-section structure:
   - 01 Context → 02 Discovery → 03 Strategy → 04 Design → 05 Outcomes → 06 Reflection
4. Add the hero stats (3 outcome cards at the top)
5. Add the meta row (Role, Timeline, Platform, Tools, Team)
6. Link the homepage work card to the new file
7. Commit and push

---

## 🤖 Working with Claude Code

This project is set up to work cleanly with Claude Code for ongoing updates.

```bash
# Install Claude Code if you haven't
npm install -g @anthropic-ai/claude-code

# Open the portfolio folder
cd kcmarshall-portfolio
claude
```

Things Claude Code can help with:
- Adding a new case study from your notes
- Swapping placeholder gradient thumbnails for real images
- Tweaking colors, spacing, or typography
- Building out the remaining case study pages
- Adding a blog/writing section
- Improving accessibility (alt tags, ARIA labels, etc.)

---

## 🎨 Design Tokens (quick reference)

| Token | Value | Used for |
|-------|-------|----------|
| `--bg` | `#0b0c0e` | Page background |
| `--bg-2` | `#111317` | Cards, sections |
| `--bg-3` | `#16191f` | Hover states |
| `--accent` | `#5de8b8` | Brand green — headlines, CTAs, stats |
| `--text` | `#f0f0ee` | Primary text |
| `--text-mid` | `rgba(240,240,238,0.55)` | Body copy |
| `--text-low` | `rgba(240,240,238,0.28)` | Labels, metadata |
| `--border` | `rgba(255,255,255,0.07)` | Subtle borders |
| `--border-m` | `rgba(255,255,255,0.12)` | Medium borders |

---

*Built March 2026 · kcmarshall.com*
