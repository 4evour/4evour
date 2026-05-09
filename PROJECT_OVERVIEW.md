# Project Overview

## Goal

This directory prepares the GitHub Profile repository `4evour/4evour`. Its `README.md` is intended to appear at the top of the GitHub user profile and show personal identity, skills, GitHub activity, latest blog posts, and a contribution snake animation.

## Stack And Services

- Markdown: main profile content.
- GitHub Actions: scheduled README and SVG updates.
- External open source components:
  - `DenverCoder1/readme-typing-svg`
  - `tandpfun/skill-icons`
  - `anuraghazra/github-readme-stats`
  - `gautamkrishnar/blog-post-workflow`
  - `Platane/snk`

## Structure

- `README.md`: GitHub profile content.
- `.github/workflows/blog-post-workflow.yml`: syncs recent blog posts from RSS into README.
- `.github/workflows/snake.yml`: generates snake SVG files and publishes them to the `output` branch.
- `PROJECT_OVERVIEW.md`: concise project notes.

## Flow

1. README embeds remote SVG components for typing text, skill icons, and GitHub stats.
2. `blog-post-workflow.yml` updates the `BLOG-POST-LIST` section from `https://4evour.github.io/rss.xml`.
3. `snake.yml` generates contribution snake SVG files and publishes them for README usage.

## Run And Test

- No local build is required.
- After pushing to `4evour/4evour`, manually run both workflows once from the GitHub Actions tab.
- The current blog RSS endpoint is `https://4evour.github.io/rss.xml`.

## Conventions

- Keep README compact and avoid too many dynamic widgets.
- The repository must be named exactly `4evour` for GitHub Profile README behavior.
- If the blog system or RSS path changes, update `.github/workflows/blog-post-workflow.yml`.

## Known Risks

- Remote SVG widgets depend on third-party services. For better stability, self-host them later.
- `github-readme-stats` may be rate-limited or temporarily return 503 from its public endpoint.
- GitHub stats and language cards are less informative while there are few public repositories.
