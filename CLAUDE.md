# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview

This is a GitHub profile repository (username/username special repository) that displays a personalized README on the user's GitHub profile page. The repository includes an automated GitHub Actions workflow to generate a snake animation from GitHub contribution graphs.

## Architecture

### GitHub Actions Workflow
- **File**: `snake..workflow` (note: this file should be moved to `.github/workflows/snake.yml` to function properly)
- **Purpose**: Generates an animated snake game SVG from the repository owner's GitHub contribution graph
- **Triggers**:
  - Scheduled every 2 hours via cron
  - Manual dispatch
  - Push to master branch (note: current branch is `main`, not `master`)
- **Output**: Creates two SVG files in the `dist/` directory and pushes them to the `output` branch
  - `github-contribution-grid-snake.svg` (light theme)
  - `github-contribution-grid-snake-dark.svg` (dark theme)

### Profile README
- **File**: `README.md`
- **Purpose**: Displays on the GitHub profile page
- **Current Content**: Basic greeting with a typing animation SVG from readme-typing-svg.demolab.com

## Important Notes

### Workflow Configuration Issue
The GitHub Actions workflow file is currently named `snake..workflow` in the root directory. For it to work, it needs to be:
1. Renamed to `snake.yml` (or any `.yml` extension)
2. Moved to `.github/workflows/` directory

### Branch Name Mismatch
The workflow is configured to trigger on pushes to the `master` branch, but the repository uses `main` as the default branch. This should be updated to `main` in the workflow file.

## Repository Structure

```
zztyac/
├── README.md              # Profile README displayed on GitHub
└── snake..workflow        # GitHub Actions workflow (needs to be moved)
```

When the workflow is properly configured, it will also create:
```
.github/
└── workflows/
    └── snake.yml          # Proper location for the workflow
```
