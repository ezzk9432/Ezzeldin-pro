# 🔐 Ezzeldin Amr – Portfolio Website

> **Cybersecurity & IT Specialist** · SOC Operations · Penetration Testing · Network Security · Medical OT

[![Live Demo](https://img.shields.io/badge/Live_Demo-Visit_Site-00e5ff?style=for-the-badge&logo=github)](https://ezzk9432.github.io)
[![Made with](https://img.shields.io/badge/Made_with-HTML_CSS_JS-7c3aed?style=for-the-badge)]()
[![GSAP](https://img.shields.io/badge/Animations-GSAP_3.12-00ff88?style=for-the-badge)]()

---

## ✨ Features

| Feature | Description |
|---|---|
| 🖥️ **Normal Mode** | Full-page portfolio with smooth scroll animations |
| ⌨️ **CLI Terminal Mode** | Hacker-style terminal interface with real commands |
| 🌧️ **Matrix Rain** | Animated Matrix-style background (Katakana + hex chars) |
| 🎯 **Custom Cursor** | Glowing dot cursor with a lagging ring follower |
| ⚡ **GSAP Animations** | ScrollTrigger reveals, hero clip-path, stagger effects |
| 🔗 **Social Sidebar** | Floating sidebar with all contact/social links |
| 📱 **Fully Responsive** | Works on mobile, tablet, and desktop |
| 🎬 **Loading Screen** | Animated percentage loader with hacker messages |

---

## 🖥️ CLI Commands

Switch to **CLI Mode** and type any of these:

```
help            → Show all available commands
whoami          → Basic info about Ezzeldin
summary         → Professional summary
experience      → Full work history
education       → Academic background
projects        → Notable projects
skills          → Technical skills by category
certifications  → Professional certifications
contact         → All contact & social links
clear           → Clear the terminal
```

**Bonus shortcuts:**
- `Tab` → Autocomplete commands
- `↑ ↓` Arrow keys → Command history

---

## 🚀 Deploy to GitHub Pages (5 Minutes)

### Step 1 — Create Repository
```bash
# Option A: Name it exactly your-username.github.io for root URL
# Option B: Any name like "portfolio" or "cv"
```

Go to [github.com/new](https://github.com/new) and create a new **public** repo.

### Step 2 — Upload the file

**Via GitHub UI (easiest):**
1. Open your new repo
2. Click **"Add file"** → **"Upload files"**
3. Drag and drop `index.html`
4. Click **"Commit changes"**

**Via Git CLI:**
```bash
git init
git add index.html
git commit -m "🚀 Initial portfolio launch"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/YOUR-REPO.git
git push -u origin main
```

### Step 3 — Enable GitHub Pages
1. Go to your repo → **Settings**
2. Scroll to **"Pages"** in the sidebar
3. Under **Source**, select **Branch: `main`** → folder: `/ (root)`
4. Click **Save**

### Step 4 — Visit your site 🎉
```
https://YOUR-USERNAME.github.io/YOUR-REPO-NAME
```
> ⚠️ It may take **1–3 minutes** to go live after enabling Pages.

---

## 📁 File Structure

```
📦 your-repo/
 ┗ 📄 index.html     ← Everything is in this single file
```

No build tools. No npm install. No frameworks to set up. Just one HTML file.

---

## 🔗 Social Links Included

| Platform | Handle |
|---|---|
| 📘 Facebook | [facebook.com/ezz206](https://www.facebook.com/ezz206) |
| 💼 LinkedIn | [Ezzeldin Amr](https://www.linkedin.com/in/ezzeldin-amr-32ab31318) |
| 📸 Instagram | [@ezzeldin_amr](https://www.instagram.com/ezzeldin_amr) |
| 💬 WhatsApp | [+201286314553](https://wa.me/201286314553) |
| 📧 Gmail | [ezz9432@gmail.com](mailto:ezz9432@gmail.com) |

---

## 🛠️ Built With

- **HTML5 / CSS3 / Vanilla JS** — Zero dependencies at runtime
- **[GSAP 3.12](https://gsap.com/)** — ScrollTrigger, TextPlugin, timeline animations
- **[Google Fonts](https://fonts.google.com/)** — Syne (display) + JetBrains Mono (code)
- **Canvas API** — Matrix rain effect
- **CSS Custom Properties** — Theming system

---

## 🎨 Customization

To update content, open `index.html` and edit:

| What to change | Where |
|---|---|
| Name, title, location | `hero` section + `D.about` object in JS |
| Work experience | `.tl-item` divs + `D.exp` array in JS |
| Projects | `.proj-card` divs + `D.proj` array in JS |
| Skills | `.chip` elements + `D.skills` object in JS |
| Social links | `#social-sidebar` + `#contact` section + `D.social` in JS |
| Color theme | `:root` CSS variables at top of `<style>` |

---

## 📸 Preview

```
┌────────────────────────────────────────────┐
│  ● EZZ.AMR // PORTFOLIO    [⬛ Normal] [▶ CLI] │
├────────────────────────────────────────────┤
│                                            │
│  Cybersecurity & IT Specialist             │
│                                            │
│  EZZELDIN                                  │
│  AMR           ┌──────────────┐            │
│                │  ● Open Work │            │
│  SOC · Pentest │  Available   │            │
│  NetSec · OT   └──────────────┘            │
│                                            │
│        [ scroll ↓ ]                        │
└────────────────────────────────────────────┘
```

---

## 📄 License

MIT — free to use, fork, and adapt.

---

<p align="center">Made with 🔐 by <strong>Ezzeldin Amr Abdelghane</strong> · Cairo, Egypt 🇪🇬</p>
