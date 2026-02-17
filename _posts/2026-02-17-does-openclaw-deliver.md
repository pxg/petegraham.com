---
title: Does OpenClaw Deliver?
date: 2026-02-17
layout: post
---

There's been a huge amount of hype recently about (OpenClaw)[https://openclaw.ai/]. You may heard it called OpenClaw/Moltbot/The artist formerly known as ClawdBot. It's the AI bot that's been taking the tech world by storm, tech bros have been buying mac minis in their droves to install OpenClaw and use it to automate all sort of aspects of their lives, from buying groceries to sending messages to their girlfriends. Which I find in equal parts dystopian and intriguing.

[Insert mac mini meme]

The concept is fairly simple you use a messaging service such as WhatsApp, Signal or Telegram to talk to your OpenClaw instance, this can either run on hardware you own such as your laptop or a mac mini, or a cloud server. OpenClaw is then powered by an LLM, it started with just support for Anthropics Claude, but now support many different models such as Google Gemini and OpenAI.

Where things get interesting is OpenClaw has memory and learns about you overtime, it then proactively starts to do tasks for you, which some people report is eerily human.

[uncanny valley meme?]

For sometime I've wanted an AI based TaskAI manager, I started vibe coding one last year, I still have the domain TaskAI.it gathering dust, at the time found LLMs weren't quite ready to automate many of the tasks I wanted. With projects like OpenClaw it feels like AI may be ready to deliver on this promise. 

OpenClaw has the ability to install and learn skills and so can apparently do things such as your shopping for you, which sounds fascinating as well as terrifying. Where a lot of the negative hype came in was from a security perspective, people had been installing OpenClaw on their laptops where it had potentially full access to almost everything they could do.

I decided to give it a spin to see what it could do. I've opted to install it on a Cloud Server as this felt much safer [virtualisation could have been good, name].

## First Attempt
I used the official one click security hardened OpenClaw installation made by Digital Ocean https://marketplace.digitalocean.com/apps/openclaw this can be installed on a standard server, which costs ~$28 per month. The image runs on Ubuntu and you connect to be ssh.

I went through the initial set-up which was fairly painless apart from a bit of of security faff to access the OpenClaw webUI.
[insert photo]

I configured it to use use the Antropic API, by default it was using the Opus model which is expensive, I wanted to use Sonnet so it would cost me less. I tried to change the model and it was very fiddly and required me editing config files in vim, restarting the Openclaw service, and generally dicking about in the terminal. OpenClaw itself wasn't very useful at giving information as in the security hardened installation it's locked down so out-of-the-box it can't access the internet. Trying to grant OpenClaw internet access was equally fiddly. I lost track of the amount of times I ran `openclaw gateway restart`.

OpenClaw does support fallback models but it doesn't support switching them easily, I was surprised at this as was expecting it to support models suited to different tasks. I was also expecting cost tracking of LLM tokens built-in, although I do believe there's a skill for this. 

At this point I was finding the experience pretty disappointing and frustrating, however I've still felt OpenClaw has a lot of potential so went with a different slightly more Yolo method.

[Yolo meme]
## Second Attempt
I started with a Ubuntu droplet on Digital Ocean, once you ssh you can install OpenClaw with `curl -fsSL https://openclaw.ai/install.sh | bash` which steps you through an installation wizard, I decided to call my bot Josh. By default OpenClaw then runs in TUI, it's Terminal UI for chat, , I did find it a fun experience chatting with Josh and can see why being have been getting hooked on this.

I then configured it to work with a Signal bot which works after quite a bit of messing about. I did find that OpenClaw sometimes hung or didn't reply to messages, it definitely didn't feel a robust experience.

I manage to grant this OpenClaw installation access to the internet I then changed it's model to [the free/cheap Google One] so it didn't cost me a fortune.

Like some people, I found OpenClaw isn't great being asked to do lots of things to do at once, so I instructed it to keep a files of all the project and task I wanted us to work on together.

To be truly collaborative I thought it would be good if we could both edit the files using Git and sync them using Github. To test OpenClaw's limits I tried to get it to sign-up for a Github account, it was unable to do this so I created an account for it myself. I then asked it to create a git repo and create ssh keys which I could associate with its Github account. It failed miserably to do this, maybe it's because I was using the cheaper google [name] model, this was pretty disappointing, and not the Skynet style experiene I expecting.

[terminator meme]

At this point I decided to stop, step back and think about what I wanted to achieve. 

## What do you want to do today?
Firstly, as an experiment, I wanted OpenClaw to retrieve some information from my calendar and create some calendar events for me, it turns out Google Gemini support this if you're using Google Calendar.

I then thought about my desire to collaborate on projects and assign tasks to agents, and co-author documents. What struct me was that I can likely get most of the behaviour I want from OpenClaw using a combination of Cursor, Cursor Agents (which I've been using), Github and potentially some custom github actions for specialised agent workflow, this is what I plan to experiment with and write about next.

OpenClaw promises a lot, but to me at this point it feels a bit too much like tech proof of concept rather than a tool ready for mainstream adoption. To be fair, maybe my mental model of how it would work was different from what it does and I need to event my own TaskAI solution.

---

Gemini pro can access your Github repo so can use them as a datasource.

. Ideally should be able to switch. Ideally should give me a breakdown of usage
	- Tried to change model and give it access to the internet, very fiddly, poor user experience. Realised I could do the simple calendar tasks I wanted to do with Gemini
	- 

- Second try start with Ubuntu image for droplet
	- `curl -fsSL https://openclaw.ai/install.sh | bash`

---

I want to be able to collaborate with AI agents on projects and have them complete tasks for me.

I thought the idea of OpenClaw was very promising but found it incredibly fiddly to set up and disappointing in term of what it can actually deliver

[it can do a lot but it takes a lot of messing about to configure it and isn't always that robust once it's been configured)]

I think a good solution would be to work in markdown, have folders for projects and files that both the AI agents and myself work on.

I'm now wondering if I should work on this in an development tool such as Cursor instead of fighting with OpenClaw.

If I did this can I:
1. Have different agents pick up different tasks or am I tied to one agent in cursor?
2. Have everything run cloud based? If I did this how would I run the agents, with GitHub actions?
