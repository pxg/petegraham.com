---
title: Cursor Cloud Agents Code While You Sleep
date: 2026-03-05
layout: post
image: /assets/images/posts/agents-while-you-sleep-hero.jpg
---

The dream is simple: use Cursor Cloud Agents to code while you sleep. Or, in my case last Friday, while walking to the pub.

I wrote about [my initial impressions using Cursor Agents](/cursor-agents/) recently. I was impressed but there was still friction in the workflow, I could ask an agent to make changes, but I still had to pull the branch on my laptop and run everything locally to check it actually worked.

That was fine for occasional use, but not exactly the mobile-first, get-shit-done anywhere workflow I was aiming for.

![Robocop coding on a MacBook while a man sleeps on his shoulder in an airplane cabin](../assets/images/posts/robocop-cloud-agents-plane.jpg)

Above is a real-life photo of one of my Cursor Agents writing code for me while I sleep, this is definitely a real image and not AI generated. Oddly the Cursor Agent is sometimes strangely preoccupied with US law enforcement, I'm yet to get to the bottom of this.

## The big upgrade: deploy previews from agent-created PRs

Next step was getting Cloud Agents to set up GitHub deploy previews for pull requests using GitHub Actions, which was a massive improvement, so much so I wrote [an article](/github-pr-previews/) about it. Now when an agent opens a PR, I can review the code and the live preview without needing to run anything locally first. Before this, "reviewing" meant reading diffs and guessing. Now reviewing means opening the preview on my phone and testing the changes.

## The bit that feels like the future

The most impressive part of Cursor Cloud Agents is the VM setup and testing workflow. It doesn't just edit files and hope for the best. It can run checks, test the change, and even record videos of manual walkthroughs. That means I can ask for design tweaks, then watch proof of what changed, while I'm on the go.

That feels like a peek of the future: Part man. Part machine. Part agentic CI pipeline.

This has been particularly useful developing this website, if I ask for a navigation tweak or spacing change, I can review the result of what it looks like on desktop by watching a video on my phone. No remote desktop hacks, no SSH gymnastics, no "I'll check later when I'm back at my laptop.".

## iPhone workflow: very close, not perfect

Using a combination of the [Cursor Agents](https://cursor.com/agents) and [GitHub](https://github.com/) web apps is already a very good solution on mobile as they both have responsive UIs. I'd still love a proper native iPhone app experience for the Cursor Cloud Agent workflow, especially around reviewing diffs, previews and videos in one smooth flow. The GitHub mobile app can help, but there is still some tab-hopping and minor faff between tools.

The big takeaway is that reviewing changes from an iPhone now genuinely works and is a practical rather than a tech demo novelty, this was not true a few months ago.

## What works and what doesn't

### 1) Work in small increments

Cloud Agents are very good most of the time, but you get better results with tighter scope, small prompts, small PRs and quick feedback loops. If I try to bundle too much in one go, quality drops and review gets harder.

### 2) "If it's worth doing, it's worth doing badly" is useful here

This is a catchphrase popularised by fellow tech enthusiast Wilf Grainger, get the rough version done first then iterate. Cloud Agents are fantastic at accelerating that loop: draft, test, review, tweak. Then you can iterate and add polish once you've validated the first version.

### 3) Usage limits are real

If you run lots of agents, you will find the limits. It's very easy to use up tokens because it's so easy to collaborate with the Cloud Agents, since starting last Friday I've merged over a dozen Cursor-generated PRs.

At one point it felt like rate limits were to Cursor Cloud Agents what stairs are to ED209.

![ED209 failing on stairs](../assets/images/posts/ed209-stairs.gif)

An exciting update is the kind people at Cursor decided to give me $100 in Cloud Agent tokens, I'm not sure if it was because they were impressed by my thought leadership in such articles.

## What I'm trying next

The next experiment is building an app with Cursor Cloud Agents rather than just iterating on a website. I also want to try more plugins/tools in that workflow, including the credit-card-related one, to see where the boundaries are right now.

My current take: this is early days but already useful and weirdly good on mobile. The workflow isn't perfect, but it's absolutely heading in the right direction, and I can see this become standard functionality offered by Claude, GitHub Copilot and the other big players.
