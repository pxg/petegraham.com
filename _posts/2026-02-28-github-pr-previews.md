---
title: GitHub Pages PR Previews
date: 2026-02-28
layout: post
image: /assets/images/posts/IMG_8868.png
---
I've been [using Cursor Cloud Agents](/cursor-agents/) to develop this site, which means I'm often reviewing pull requests (PRs) from my phone. The missing piece in my workflow was a way for each PR to have a preview site so I could test the changes allowing me to then merge them with confidence. I've now set this up using GitHub actions.

![](/assets/images/posts/pr_preview_workflow.svg)

## What I wanted

The goal was simple:

1.  Keep automated deploys to production by pushing to the main branch
2.  Generate a preview URL for each pull request
3.  Clean up preview files automatically when the PR is closed

## How it works

This is achieved with two [GitHub Actions workflows](https://github.com/pxg/petegraham.com/tree/main/.github/workflows). The first workflow handles the normal production deploys on pushes to the `main` branch. This is the standard for how GitHub pages works out-of-the-box. The new workflow builds the changes on `main` and pushes them to the `gh-pages` deployment branch.

The second workflow runs on pull request events (opened, reopened, synchronize, and closed). For open PRs, it builds Jekyll with a PR-specific base URL like [https://petegraham.com/pr-preview/pr-13/](https://petegraham.com/pr-preview/pr-13/). Because the source code for this site is public I'm comfortable with the preview sites also being available publicly.

That base URL is important so CSS, links, and assets resolve correctly under the preview path. After building, the workflow deploys `_site` on the `gh-pages` branch into a subdirectory for the PR:
```
gh-pages/pr-preview/pr-<PR_NUMBER>/
```

When the PR is closed, the same workflow removes that preview directory.

## Don't nuke PR sites with production deploys!

My main deploy workflow now excludes the preview umbrella directory from clean-up (`clean-exclude: pr-preview`). Without that, a regular deploy to `main` can wipe all preview sites.

![](/assets/images/posts/pr_preview_gh_pages_layout.svg)

So the setup works because the two workflows cooperate:

*   main deploy publishes the production site
*   PR deploy publishes preview folders
*   preview folders are preserved until a PR is closed

## One-time GitHub settings

I also had to make sure repository settings matched the workflow expectations:

*   GitHub Pages source set to `gh-pages` (root)
*   Actions workflow permissions set to read and write

Without write permissions, the preview action can't publish to `gh-pages` or comment preview links on pull requests.

## Result

Now each pull request gets a working preview URL in the PR conversation, and I can review content/layout changes before merging. It's a relatively small change, but it makes the whole mobile first development process feel much smoother.