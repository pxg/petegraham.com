---
layout: til
title: "Today I learnt about Extracting Notes in Obsidian 📝"
date: 2026-02-19
---

I do a lot of planning and note taking in [Obsidian](https://obsidian.md/). Occasionally, some of my notes get a bit long and benefit from being broken up into multiple files. When I do this, I like to link the notes to avoid extracting the information and forgetting about it.

This can be done manually, but there's a handy Obsidian plugin that makes it easier. This can be installed by going to *Settings > Community plugins*, then searching for "Note Refactor" and installing it.

![Obsidian Community Plugins browser showing Excalidraw, Templater, Dataview, Tasks, and Git](/assets/images/til/obsidian_note_refactor.png)

Once installed, it's simple to extract a note:
- Highlight the section of the note you want to extract
- Click `CMD + P` 
- Select *"Note Refactor: Extract selection to new note - first line as file name"* from the menu

![Screenshot showing the Obsidian command palette, with "Note Refactor: Extract selection to new note - first line as file name" highlighted, plus other related commands and options visible. This is exactly what you’ll see when you trigger CMD+P.](/assets/images/til/obsidian_note_refactor_command.png)

A new file will be created based on the first line of your extracted section, this note will open, and a link to it will be added to the original.

![Screenshot: Obsidian note showing a "Links" section with two links, "This Week" and "PeteGraham.com", styled as clickable Markdown links.](/assets/images/til/obsidian_note_refactor_links.png)