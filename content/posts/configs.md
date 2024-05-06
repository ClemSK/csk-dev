---
title: "Configs"
date: 2024-03-02T08:52:43Z
draft: true
tags:
- configs
- unix
- backups
---

At work and in my own time (partially by triggered by using neovim)

- terminal emulator
- shell
    - .zshrc
- dotfiles
    - git
- editor
    - vs code / nvim
- programs 

Very useful way of reinstalling the packages installed using brew. Take a text file and run a script to install the cli tools / programs. it's also possible to add things like Spotify, Whatsapp and Slack to the list of programs installed by Brew. 

```
brew leaves > my_brew.txt
xargs brew install < my_brew.txt
```

Backing up VS code: 
- json settings

