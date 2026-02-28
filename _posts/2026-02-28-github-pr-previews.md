---
title: GitHub pages PR Previews
date: 2026-02-28
layout: post
---
I've been using Cursor Cloud Agents to develop this site, which means I'm often reviewing changes in PRs (pull requests) from my phone. The missing piece in my workflow was a way for each PR to have a live preview link so I could test changed and merge with confidence. I’ve now set this up using GitHub actions.

!\[\]({{ "/assets/images/posts/pr\_preview\_workflow.svg" | relative\_url }})

High-level PR preview lifecycle: build, publish, comment, clean up.

## What I wanted

The goal was to keep things simple:

1.  Keep normal deploys to `main` exactly as they are
    
2.  Generate a preview URL for each pull request
    
3.  Clean up preview files automatically when the PR is closed
    

## How it works

I split things into two GitHub Actions workflows.

The first workflow handles the normal site deploy to `gh-pages` on pushes to `main`.

The second workflow runs on pull request events (`opened`, `reopened`, `synchronize`, and `closed`). For open PRs, it builds Jekyll with a PR-specific base URL like:

`/pr-preview/pr-<PR_NUMBER>`

That base URL is important so CSS, links, and assets resolve correctly under the preview path.

After building, the workflow deploys `_site` into a subdirectory on `gh-pages`:

`gh-pages/pr-preview/pr-<PR_NUMBER>/`

When the PR is closed, the same workflow removes that preview directory.

## The one detail that saves headaches

My main deploy workflow now excludes the preview umbrella directory from clean-up (`clean-exclude: pr-preview`). Without that, a regular deploy to `main` can wipe all preview sites.

!\[\]({{ "/assets/images/posts/pr\_preview\_gh\_pages\_layout.svg" | relative\_url }})

How production files and PR preview folders coexist on `gh-pages`.

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

Now each pull request gets a working preview URL in the PR conversation, and I can review content/layout changes before merging. It's a small change, but it makes this mobile first development process feel much easier.