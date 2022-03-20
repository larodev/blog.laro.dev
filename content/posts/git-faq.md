---
title: "Git FAQ"
tags:
- git
date: 2022-03-20
toc: true
draft: false
---

These are questions that I've had when working with git. 

#### Use different author info for each repo

Using the git commands:

```git
git config user.name yourusername
git config user.email your@mail.com
```

They will take over the values you might have set in the `--global` configuration.

#### How to change the username and email of previous commits

```shell
git rebase -i HEAD~40 -x "git commit --amend --author 'Author Name <author.name@mail.com>' --no-edit"
```
From [Change git email for previous commits](https://stackoverflow.com/questions/34850831/change-git-email-for-previous-commits)

- Replace `40` with the number of commits. You can calculate this with `git rev-list --count master` minus 1
- Keep the `<>` around the email