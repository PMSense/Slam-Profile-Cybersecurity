# laqtib.com

Source for my personal site — a cybersecurity/product portfolio, plus a small set of longer-form technical field guides and coursework projects. Built as static HTML/CSS (no framework, no build step) and deployed via GitHub Pages.

**Live site:** [laqtib.com](https://laqtib.com)

> **Note on visibility:** the site is intentionally excluded from search engines (`robots.txt` + `noindex` on every page), but it is not access-restricted — anyone with a direct link can view any page. Treat it as "unlisted," not "private."

## Site map

| Page | File | Description |
|---|---|---|
| Home | `index.html` | Profile, professional summary, areas of expertise, technical skills |
| Professional Experience | `professional-experience.html` | Work history |
| Cybersecurity | `cybersecurity.html` | Cybersecurity-focused background |
| ML & AI Security | `ai-security.html` | AI/ML security background, links to the Stanford field guide |
| Education | `education.html` | Degrees, coursework, and Berkeley research summaries |
| Engineering | `engineering.html` | Cryptographic systems, KMS/HSM, full-stack work |
| Data Protection | `data-protection.html` | Privacy, governance, and data protection topics |
| Projects | `projects.html` | Hands-on notebooks and coursework (links into `notebooks/`) |
| More.. | `more.html` | Catch-all: links, Articles, Photos, Videos |

## Field guides

Longer-form reference documents, each built as a standalone HTML document (own typography system, sticky section nav, glossary) and embedded into the main site via a thin nav + `<iframe>` wrapper page so they keep the site's navigation:

| Wrapper page | Content file | Source |
|---|---|---|
| `stanford-ai-security-guide.html` | `ai_security_field_guide.html` | Stanford Advanced Cybersecurity Program (XACS134) |
| `berkeley-applied-ml-guide.html` | `applied_ml_field_guide.html` | UC Berkeley coursework |
| `identity-debt-guide.html` | `identity_debt_field_guide.html` | Research paper — *Rethinking Identity Security in the Age of Deepfakes and Autonomous AI* |
| `cloud-security-engineering-guide.html` | `cloud_security_engineering_field_guide.html` | Final project, Cyber 290 — *Comprehensive Cloud Security Engineering* |

## Projects / notebooks

Coursework Jupyter notebooks live in `notebooks/` and are linked from `projects.html`:

- `Poisoning_Attack_Pipeline_vFinal3.ipynb`
- `Slam_Laqtib_project1_2.ipynb` – `project4_1.ipynb`

## Structure & conventions

- **Single shared stylesheet** — `style.css`, loaded on every page as `style.css?v=N`. The version query string is a manual cache-buster: bump `N` any time `style.css` changes, since browsers and GitHub's CDN cache the file by exact URL.
- **Field guides are self-contained** — the `*_field_guide.html` content files have no `<html>`/`<head>` wrapper; they're designed to be dropped into an `<iframe>` and carry their own fonts (Google Fonts: IBM Plex Sans/Serif/Mono) and CSS variables, independent of `style.css`.
- **Favicons** — `favicon.svg` / `favicon.ico` / `favicon-16x16.png` / `favicon-32x32.png` / `apple-touch-icon.png`, all referenced from every page's `<head>`.
- **SEO opt-out** — `robots.txt` (`Disallow: /`) plus `<meta name="robots" content="noindex, nofollow">` on every page, including the field-guide content files.

## Deployment

Hosted on **GitHub Pages**, deployed via a **GitHub Actions** workflow that publishes the repository root on every push to `main`. The custom domain (`laqtib.com`) is configured in the repo's Pages settings. There's no build step — HTML/CSS/assets are served as-is.

To update the live site: edit locally, commit, and push to `main` — the Pages deployment runs automatically.
