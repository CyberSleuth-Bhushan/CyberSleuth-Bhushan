# Setup & Deployment Guide

Complete instructions for deploying this GitHub Profile README.

---

## Prerequisites

- [Git](https://git-scm.com/) installed on your machine
- A [GitHub](https://github.com) account
- Your GitHub username: `CyberSleuth-Bhushan`

---

## Step 1 — Create the Profile Repository

GitHub displays a special README on your profile when you create a repository with the **same name as your username**.

Your profile repository already exists at:

```
https://github.com/CyberSleuth-Bhushan/CyberSleuth-Bhushan
```

If it doesn't exist, create it:

1. Go to [github.com/new](https://github.com/new)
2. Repository name: `CyberSleuth-Bhushan`
3. Set to **Public**
4. Check **Add a README file**
5. Click **Create repository**

---

## Step 2 — Clone & Replace Files

```bash
# Clone your profile repository
git clone https://github.com/CyberSleuth-Bhushan/CyberSleuth-Bhushan.git

# Navigate into the repository
cd CyberSleuth-Bhushan
```

Now copy all the files from this project into the cloned repository:

```bash
# From the project directory, copy everything:
# - README.md
# - SETUP.md
# - assets/
# - .github/
```

Your repository should look like this:

```
CyberSleuth-Bhushan/
├── README.md
├── SETUP.md
├── assets/
│   └── README-assets/
│       ├── hero-banner.svg
│       ├── divider.svg
│       ├── footer.svg
│       └── profile.png
└── .github/
    └── workflows/
        └── contribution-snake.yml
```

---

## Step 3 — Replace Placeholders

Search for and replace these placeholders in `README.md`:

| Placeholder | Replace With |
|---|---|
| `YOUR_LEETCODE_USERNAME` | Your LeetCode username |
| `YOUR_CODEFORCES_USERNAME` | Your Codeforces username |
| `YOUR_HACKERRANK_USERNAME` | Your HackerRank username |

If you don't use a platform, **delete that badge entirely** from the Coding Profiles section.

### How to search:

```bash
# Find all placeholders
grep -rn "YOUR_" README.md
```

---

## Step 4 — Push to GitHub

```bash
# Stage all files
git add -A

# Commit
git commit -m "✨ Complete profile README redesign"

# Push to main branch
git push origin main
```

---

## Step 5 — Enable GitHub Actions (Contribution Snake)

The contribution snake animation requires GitHub Actions to generate the SVG.

### 5.1 — Set Workflow Permissions

1. Go to your repository: `https://github.com/CyberSleuth-Bhushan/CyberSleuth-Bhushan`
2. Click **Settings** → **Actions** → **General**
3. Scroll to **Workflow permissions**
4. Select **Read and write permissions**
5. Click **Save**

### 5.2 — Trigger the Workflow

1. Go to the **Actions** tab in your repository
2. Click on **Generate Contribution Snake** in the left sidebar
3. Click **Run workflow** → **Run workflow**
4. Wait for the workflow to complete (usually under 2 minutes)

### 5.3 — Verify

After the workflow runs:

1. Check that a new branch called `output` was created
2. The `output` branch should contain:
   - `github-snake.svg` (light mode)
   - `github-snake-dark.svg` (dark mode)
3. Visit your profile to verify the snake animation appears

The workflow runs **automatically every day at midnight UTC** to keep the animation current.

---

## Step 6 — Verify Your Profile

Open your profile: [github.com/CyberSleuth-Bhushan](https://github.com/CyberSleuth-Bhushan)

### Checklist

- [ ] Hero banner SVG renders correctly
- [ ] Profile photo displays (circular)
- [ ] Typing animation plays
- [ ] All profile link badges are clickable and correct
- [ ] About Me section renders with the YAML code block
- [ ] "What I'm Up To" section shows current activities
- [ ] Tech stack badges render with correct icons
- [ ] Featured project cards load from github-readme-stats
- [ ] GitHub Stats card shows your statistics
- [ ] GitHub Streak card shows your streak
- [ ] Top Languages card displays correctly
- [ ] Contribution snake animation appears (after Actions setup)
- [ ] Coding profile badges link to your actual profiles
- [ ] Connect section badges are all clickable
- [ ] Footer SVG renders
- [ ] Profile views counter appears
- [ ] No broken images or badges
- [ ] No placeholder text remains (unless intentional)
- [ ] Mobile rendering looks clean

---

## Troubleshooting

### Snake animation not showing

1. **Workflow hasn't run yet** — Trigger it manually from the Actions tab
2. **Permissions issue** — Ensure workflow permissions are set to "Read and write"
3. **Branch not created** — Check if the `output` branch exists
4. **Image blocked by ISP** — Some ISPs in India block `raw.githubusercontent.com`. Try with a VPN.

### GitHub Stats cards not loading

1. **Rate limiting** — The public API can be rate-limited. Wait a few minutes and refresh.
2. **Username issue** — Verify that `CyberSleuth-Bhushan` is spelled correctly in all URLs.
3. **Self-host option** — Deploy your own instance on Vercel using [github-readme-stats](https://github.com/anuraghazra/github-readme-stats).

### Streak stats not showing

1. **Service downtime** — `streak-stats.demolab.com` occasionally has downtime. Wait and retry.
2. **Timezone** — Stats use UTC. Late-night contributions may appear on the next day.

### Profile photo not circular

GitHub Markdown doesn't support the CSS `border-radius` property in `style` attributes. The photo will appear **square on GitHub**. This is a known limitation. The photo still displays correctly.

> **Tip:** If you want a circular photo, crop the image to a circle with a transparent background using an image editor, then replace `profile.png`.

---

## Customization Tips

### Change color scheme

The profile uses a consistent color palette:

| Color | Hex | Usage |
|---|---|---|
| Background | `#0d1117` | Dark background |
| Primary | `#58a6ff` | Links, accents |
| Secondary | `#bc8cff` | Highlights, gradient |
| Text | `#c9d1d9` | Body text |
| Muted | `#8b949e` | Secondary text |
| Border | `#30363d` | Subtle borders |

To change colors, search and replace the hex codes in:
- `README.md` (badge URLs and stats card parameters)
- `assets/README-assets/hero-banner.svg`
- `assets/README-assets/divider.svg`
- `assets/README-assets/footer.svg`

### Add a new project

Add this block in the Featured Projects section:

```html
<a href="https://github.com/CyberSleuth-Bhushan/REPO_NAME">
  <img src="https://github-readme-stats.vercel.app/api/pin/?username=CyberSleuth-Bhushan&repo=REPO_NAME&theme=tokyonight&hide_border=true&bg_color=0d1117&title_color=58a6ff&icon_color=bc8cff&text_color=c9d1d9" alt="Project Name"/>
</a>
```

### Add a new technology badge

Use this format:

```markdown
![TechName](https://img.shields.io/badge/LABEL-HEXCOLOR?style=for-the-badge&logo=LOGO_NAME&logoColor=fff)
```

Find logo names at [simpleicons.org](https://simpleicons.org/).

---

## Quick Commands Reference

```bash
# Clone
git clone https://github.com/CyberSleuth-Bhushan/CyberSleuth-Bhushan.git
cd CyberSleuth-Bhushan

# After making changes
git add -A
git commit -m "Update profile README"
git push origin main

# Check for remaining placeholders
grep -rn "YOUR_" README.md
```
