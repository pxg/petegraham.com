---
title: Cursor Agents
date: 2026-02-09
layout: post
---
I use Cursor to develop this website, [last week I set up Pages CMS](/publishing-jekyll-articles-from-an-iphone/) so I could edit and publish articles from my phone. Now most of the time I'm prompting Cursor and reviewing code, which got me wondering if I could do this whole workflow from my phone, like how I can now publish articles.

It turns out that with [Cursor Agents](https://cursor.com/agents) not only is this possible, but it works pretty well. You connect Cursor to your GitHub, after prompting it, then create a PR (pull request) with the code changes. Cursor runs the agent in the cloud for you, so you don't need to set up a remote connection to a machine running Cursor or anything like that. You can review the code on [GitHub.com](http://GitHub.com) or using the GitHub mobile app. I found the app was a slightly better experience.

![](/assets/images/posts/IMG_8778.png)

This site's GitHub repo is set up for auto-deployment on commit to main, so once I approve PRs, they get deployed, which all feels kind of auto-magical.

![](/assets/images/posts/IMG_8779.png)

One enhancement I'd like to explore is to have a development version of the site spun up for each PR so I can review.