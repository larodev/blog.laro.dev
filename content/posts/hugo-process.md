---
title: "Hugo website process"
tags:
- web
date: 2022-03-27
toc: true
draft: true
description: Static website manufacturing process using Hugo 
---

# Requirements
# Steps
## Set up repository
## Choose theme, fork repository
Optionally, change theme name, but keep pointing to the original.
## Start Hugo project

Clone empty repository and create site inside folder:

```bash
hugo new site <repo-name> --force
```
## Add theme as submodule

```bash
git submodule add <repo-url>
```
I'm using SSH to connect to GitHub, and I have more than one account. To manage this, I use different GitHub host domains: github.com-larodev, github.com-personal, github.com-work. I use the SSH host `git@github.com-larodev:larodev/laro.dev.git` to clone repos. To make it work in Netlify, I need to change the url in `.gitmodules` to point to GitHub:

```toml
BEFORE:
[submodule "themes/laro.dev"]
	path = themes/laro.dev
	url = git@github.com-larodev:larodev/laro.dev.git
AFTER:
[submodule "themes/laro.dev"]
	path = themes/laro.dev
	url = https://github.com/larodev/laro.dev
```
