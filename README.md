# 🔐 Ezzeldin Amr — Portfolio v4.0

> **Cybersecurity & IT Specialist** · SOC Operations · Penetration Testing · Network Security · Medical OT

[![Live Demo](https://img.shields.io/badge/Live_Demo-GitHub_Pages-00e5ff?style=for-the-badge&logo=github)](https://ezzk9432.github.io/Ezzeldin-pro/)
[![Made with](https://img.shields.io/badge/Made_with-HTML_CSS_JS-7c3aed?style=for-the-badge)]()
[![GSAP](https://img.shields.io/badge/Animations-GSAP_3.12-00ff88?style=for-the-badge)]()
[![Modes](https://img.shields.io/badge/Modes-Normal_%7C_CLI-ffd700?style=for-the-badge)]()
[![Theme](https://img.shields.io/badge/Theme-Dark_%7C_Light-ff8c42?style=for-the-badge)]()

---

## ✨ What's New in v4.0

| Feature | Description |
|---|---|
| ▶ **CLI Terminal Mode** | Full hacker-style terminal with 13 real commands |
| ☀ **Dark / Light Theme** | Toggle between dark matrix mode and clean light mode |
| 📊 **Analysis Page** | Visual domain expertise bars, career timeline, tech stack bubbles |
| ⚡ **Skill Proficiency Bars** | Animated horizontal bars showing skill levels |
| 🔒 **All Email Links Fixed** | Direct `mailto:` links — no more Cloudflare CDN 404s |
| 🖼 **7 Navigation Cards** | Added Analysis section as card 06 |
| 🌧 **Matrix Rain** | Fades gracefully in light mode |
| 🎯 **Custom Cursor** | Glowing dot + ring follower, `mix-blend-mode: difference` |
| ⚡ **GSAP Animations** | Hero clip-path reveal, card stagger, page transitions |
| 📱 **Fully Responsive** | Mobile, tablet, and desktop |
| 🔗 **Social Sidebar** | Always-visible fixed sidebar — icons guaranteed visible |

---

## 🖥️ CLI Terminal Commands

Switch to **CLI Mode** (top bar → `▶ CLI`) and type any command:

```
help             → Show all available commands
whoami           → Identity & contact info
summary          → Professional overview
experience       → Full work history (all 5 roles)
education        → Degrees, GPA, graduation project
projects         → All 5 projects with tech stacks
skills           → Full skill breakdown by category
certifications   → All 4 professional certifications
contact          → All social links & contact details
ls               → List available sections
date             → Current date & time
clear            → Clear the terminal
exit             → Return to Normal mode
```

**Keyboard shortcuts:**
| Key | Action |
|---|---|
| `Tab` | Autocomplete command |
| `↑` / `↓` | Browse command history |
| `Enter` | Execute command |
| `Esc` | Switch back to Normal mode |

---

## 🎨 Theme Toggle

Click the **☀ / 🌙** button in the top bar to switch themes.

| Dark Mode | Light Mode |
|---|---|
| `#020912` deep navy background | `#f0f5fc` soft blue-white background |
| Cyan `#00e5ff` accent | Navy `#0088cc` accent |
| Matrix rain at 4% opacity | Matrix rain at 1.5% opacity (subtle) |
| Glowing green status dot | Muted green status dot |

All colors use CSS custom properties — both themes adapt every element automatically.

---

## 📊 Analysis Page

The **Analysis** section (card 06) gives recruiters and HR a visual snapshot:

- **Domain Expertise bars** — animated fills for 6 skill domains
- **Career Timeline** — visual chronological milestone list (2019 → Present)
- **Technology Stack** — colour-coded bubbles by category (blue=security, purple=tools, green=dev, yellow=systems)
- **Key Strengths** — four differentiating qualities with colour-coded highlights

---

## 🚀 Deploy to GitHub Pages (5 Minutes)

### Step 1 — Create Repository

Go to [github.com/new](https://github.com/new):
- Name it **`your-username.github.io`** → your site lives at `https://your-username.github.io`
- Or any name like `portfolio` → site at `https://your-username.github.io/portfolio`
- Set visibility to **Public**

### Step 2 — Rename & Upload

Rename `ezzeldin_portfolio_v4.html` → **`index.html`**, then:

**Via GitHub UI (easiest):**
1. Open your new repo
2. Click **Add file** → **Upload files**
3. Drag and drop `index.html`
4. Click **Commit changes**

**Via Git CLI:**
```bash
git init
git add index.html
git commit -m "🚀 Portfolio v4 launch"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/YOUR-REPO.git
git push -u origin main
```

### Step 3 — Enable GitHub Pages
1. Repo → **Settings** → **Pages** (sidebar)
2. Under **Source** → select **Branch: main** → folder: **/ (root)**
3. Click **Save**

### Step 4 — Visit your site 🎉
```
https://YOUR-USERNAME.github.io/YOUR-REPO-NAME
```
> ⚠️ Allow **1–3 minutes** for GitHub to build and publish.

---

## 📁 File Structure

```
📦 your-repo/
 ┗ 📄 index.html    ← Everything in one file. No build tools. No npm.
```

Zero dependencies at runtime except:
- GSAP 3.12 (CDN — animations)
- Google Fonts: Syne + JetBrains Mono (CDN)

---

## 🔗 Social Links

| Platform | Link |
|---|---|
| 📘 Facebook | [facebook.com/ezz206](https://www.facebook.com/ezz206) |
| 💼 LinkedIn | [Ezzeldin Amr](https://www.linkedin.com/in/ezzeldin-amr-32ab31318) |
| 📸 Instagram | [@ezzeldin_amr](https://www.instagram.com/ezzeldin_amr) |
| 💬 WhatsApp | [+201286314553](https://wa.me/201286314553) |
| 📧 Gmail | [ezz9432@gmail.com](mailto:ezz9432@gmail.com) |

---

## 🛠️ Built With

- **HTML5 / CSS3 / Vanilla JS** — zero runtime dependencies
- **[GSAP 3.12](https://gsap.com/)** — hero clip-path, page transitions, stagger reveals
- **[Google Fonts](https://fonts.google.com/)** — Syne (display) + JetBrains Mono (monospace)
- **Canvas API** — Matrix rain effect
- **CSS Custom Properties** — full dual-theme system

---

## 🎨 Customisation Guide

Open `index.html` and edit these sections:

| What to change | Where in the file |
|---|---|
| Name, role, location | `#pg-home` hero section |
| Professional summary | `#pg-summary` `.sum-box` |
| Work experience | `#pg-experience` `.tli` blocks |
| Education entries | `#pg-education` `.edu-c` blocks |
| Projects | `#pg-projects` `.proj-c` blocks |
| Skills chips | `#pg-skills` `.chips` divs |
| Skill bar percentages | `data-pct` attributes on `.bar-fill` |
| Analysis domains | `#pg-analysis` `.domain-fill` data-pct |
| Social links | `#soc` sidebar + `#pg-contact` |
| Color theme | `:root [data-theme]` CSS variables at top |
| CLI command responses | `const D = {...}` object in JS |

---

## 🖼 Preview

```
┌─────────────────────────────────────────────────────┐
│  ● EZZ.AMR // v4   [⊞ Normal] [▶ CLI] [☀] [← Back] │
├─────────────────────────────────────────────────────┤
│  ● Open to Work · Available Now                     │
│                                                     │
│  Cybersecurity & IT Specialist                      │
│                                                     │
│  EZZELDIN                                           │
│  AMR                                                │
│                                                     │
│  SOC Operations · Penetration Testing · Medical OT  │
│                                                     │
│  [ Hire Me ] [ LinkedIn ↗ ] [ Analysis ↗ ]         │
│                                                     │
│  5+ yrs  |  3.30 GPA  |  5 projects  |  4 certs    │
├─────────────────────────────────────────────────────┤
│  01 Summary  02 Experience  03 Education            │
│  04 Projects 05 Skills      06 Analysis             │
│  07 Contact                                         │
└─────────────────────────────────────────────────────┘

CLI MODE:
┌─────────────────────────────────────────────────────┐
│  ● ● ●   ezzeldin@portfolio:~ — Terminal Mode       │
├─────────────────────────────────────────────────────┤
│  ███████╗███████╗███████╗                           │
│  Ezzeldin Amr — Cybersecurity & IT Specialist       │
│  Portfolio Terminal v4.0                            │
│                                                     │
│  $ whoami                                           │
│  Ezzeldin Amr Abdelghane                           │
│  Role: Cybersecurity & IT Specialist                │
│  Status: ● Open to Work                             │
│                                                     │
│  ezzeldin@portfolio:~$ _                            │
└─────────────────────────────────────────────────────┘
```

---

## 📄 License

MIT — free to use, fork, and adapt with credit.

---

<p align="center">
  Built with 🔐 by <strong>Ezzeldin Amr Abdelghane</strong> · Sherouk, Egypt 🇪🇬<br>
  <a href="mailto:ezz9432@gmail.com">ezz9432@gmail.com</a> · <a href="https://wa.me/201286314553">+201286314553</a>
</p>
