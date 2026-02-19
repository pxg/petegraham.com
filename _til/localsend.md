---
layout: til
title: "Today I learnt about LocalSend 📤"
date: 2026-02-17
---

[LocalSend](https://localsend.org/) is a free, open-source app for sharing files over your local network—like AirDrop but cross-platform. No cloud, no account, no internet required. It uses end-to-end encryption and works between Mac, Linux, Windows, Android, and iOS.

I've been using it to send files between my Mac and a Linux Mint machine on the same network. Both devices appear in the app and you can drag-and-drop files or folders between them.

### Install on Mac

With [Homebrew](https://brew.sh/):

```
brew install --cask localsend
```

Or download the DMG from [localsend.org/download](https://localsend.org/download).

### Install on Linux Mint

**Snap** (simplest):

```
sudo snap install localsend
```

**Flatpak** (if you prefer):

```
flatpak install flathub org.localsend.localsend_app
```

You can also grab the `.deb` from the [official downloads](https://localsend.org/download) and install with `sudo dpkg -i LocalSend-*.deb`.
