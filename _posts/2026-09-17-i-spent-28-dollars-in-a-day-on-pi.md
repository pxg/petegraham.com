---
title: I Spent $28 in a Day on Pi
date: 2026-09-17
layout: post
image: /assets/images/posts/pi-pork-pies-hero.webp
image_alt: Eating a pork pie outside Eley's World Famous Hand Raised Pork Pies
---
I've been using AI software development tools for a number of years now. I was an early user of GitHub Copilot before switching to Cursor; more recently, I've been using a combination of Cursor and Claude Code. I've also dabbled with Lovable along the way.

I enjoy Claude Code's user experience of working in the terminal. I don't know why, but it just feels a bit more fun than using Cursor's IDE; maybe it just takes me back to my developer roots of configuring servers command line.

I've been meaning to try [Pi](https://pi.dev/), an open-source coding harness with a "bring your own model" philosophy, since I heard about it at [Claude Code Anonymous](https://luma.com/claude-code-brighton?period=past), a meet-up for discussing AI in Software Development.

Pi is quick to set up, and the user experience feels very similar to Claude Code; in fact, it's compatible with Claude Code configuration and skills. Developers enjoy using it as it's highly configurable, so you can make it work exactly how you want, so somewhat of a Vim philosophy but for a coding harness.

An example is that it doesn't include an in-built plan mode; instead, most people instruct it to plan using markdown files. This is how I prefer to work anyway, so plans are documented along with code, and I can collaborate on them with the LLM. 

I started by configuring it to use an Anthropic API key, meaning you are paying for usage rather than on a fixed-fee plan. This is the default way Pi works. I used Anthropic's Sonnet 5, which is an affordable model compared to Opus or the very expensive Claude Fable.

I was very much enjoying using Pi; however, it shows token spend in the UI, which made me very aware of what I was spending. Researching the most cost-effective way to use Pi, it suggested that I should pay $10 for a GitHub Copilot subscription. I burnt through this surprisingly quickly and so switched back to my Anthropic API key, which I then needed to top up with credit.

When I was wrapping up for the day, I told Pi to work on as much of the plan as it could on its own. This is something I often do when working with LLMs; it's nice to start the day in the morning and see lots of work has been done for you.

The next morning I got quite the surprise: Pi had burnt through all of my Anthropic credit and produced surprisingly little. The day's spend was $28. Thankfully I didn't have auto-top up enabled.

Some detective work into why Pi used so much credit discovered that unlike Claude Code, Pi doesn't compact conversations, so after a day in one session the context had grown to nearly 500,000 tokens, including a database dump and hundreds of shell commands, and it was re-sending all of that on every turn. About 91% of the bill was context; only 9% paid for generated text. Pi's cache also expires after five minutes by default, which made stepping away expensive, but a longer cache would only have saved about 10%. The expensive bit was never starting a fresh session. Here's the full analysis done by Claude Code [https://claude.ai/artifact/AyJpe34aGafU5avECWL44y](https://claude.ai/artifact/AyJpe34aGafU5avECWL44y).

While this was an expensive mistake, it did make me think of the cost of LLM usage; it's well known that Cursor and Anthropic are subsidising usage of their AI coding tools, as this area is currently a bit of a land grab. I was made aware of this last year when I was using AWS Bedrock and [Cline](https://cline.bot/) for a particularly sensitive project where I didn't want the code shared with another company.

For now I've switched back to Claude Code. I like the idea of using something open source, but I don't think the economics for Pi stack up for me at this point in time. I do plan on trying it with the [Claude Code plugin](https://www.npmjs.com/package/pi-claude-bridge) under the hood, which means it will bill to the Claude subscription I already have. However I think this may be a bit of a bit like a hack, from what I've read it's not as efficient as using Claude Code directly, so I'm wondering if it's worth the effort as the user experience is very similar. Perhaps if I upgrade my MacBook in future, I'll try running it again using open-weight models.
