---
title: Cursor Cloud Agents While You Sleep (or Walk to the Pub)
date: 2026-02-28
layout: post
---
The dream is simple: use Cursor Cloud Agents to code while you sleep.

Or, more realistically in my case last Friday, while walking to the pub.

I wrote about my first pass at this recently in [Cursor Agents](/cursor-agents/). That worked, but there was still friction. I could ask an agent to make changes, but then I still had to pull the branch on my laptop and run everything locally to see if it actually worked.

That was fine for occasional use, but not exactly the "mobile-first, slightly chaotic, get stuff done from anywhere" workflow I was aiming for.

## The big upgrade: deploy previews from agent-created PRs

Next step was getting Cloud Agents to set up GitHub deploy previews for pull requests using GitHub Actions. This was a massive quality-of-life improvement.

Here is the workflow it created: [Deploy PR preview workflow](https://github.com/pxg/petegraham.com/blob/main/.github/workflows/pr-preview.yml).

Now when an agent opens a PR, I can review the code and the live preview without needing to run anything locally first. That closes a huge loop for me.

Before this, "reviewing" meant reading diffs and guessing.
Now reviewing means opening the preview on my phone and seeing what actually happened.

## The bit that feels like the future

The most impressive part of Cursor Cloud Agents is the VM setup and testing workflow.

It does not just edit files and hope for the best. It can run checks, test the change, and even record videos of manual walkthroughs. That means I can ask for design tweaks, then watch proof of what changed, while I am on mobile.

That is peak (or peek) future energy.

This website is where this feels most obvious. If I ask for a navigation tweak or spacing change, I can review the result in a desktop-style preview and artifact video from my iPhone. No remote desktop hacks. No SSH gymnastics. No "I'll check later when I'm back at my laptop."

## iPhone workflow: very close, not perfect

This is already very good.

Still, I would love a proper native iPhone app experience for the Cursor Cloud Agent workflow, especially around reviewing diffs, previews and artifacts in one smooth flow.

The GitHub mobile app helps a lot, but there is still some tab-hopping and minor faff between tools.

Homepage review from an iPhone is now genuinely practical though, which was not true for me a few months ago.

## What works (for me) and what does not

### 1) Work in small increments

Cloud Agents are very good most of the time, but you get better results with tighter scope.

Small prompts. Small PRs. Quick feedback loops.

If I try to bundle too much in one go, quality drops and review gets harder.

### 2) "If it's worth doing, it's worth doing badly" is useful here

I mean this in the best possible way.

Get the rough version done first. Then iterate.

Cloud Agents are fantastic at accelerating that loop: draft, test, review, tweak. You can polish after you know the shape is right.

### 3) Usage limits are real

If you run lots of agents, you will find the limits.

I definitely have.

One useful proxy number from this repo: I have already merged 10 Cursor-generated PRs since starting this experiment in early February. That is enough volume to feel both the magic and the limits.

## What I am trying next

The next experiment is building an app with Cursor Cloud Agents rather than just iterating on a website.

I also want to try more plugins/tools in that workflow, including the credit-card-related one, to see where the practical boundaries are right now.

My current take: this is already useful, already weirdly good on mobile, and still early. The workflow is not perfect, but it is absolutely heading in the right direction.
