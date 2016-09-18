---
layout:    post
title:     "Git Notes"
date:      2016-08-25
comments:  true
tags: [Git]
---

## Purpose
This post is a git note. I will record all the problems I have met and give solution as I can do. Furthermore, it will discuss some Git Pro knowledge as I have met in work and study.


## Remember password and user name at bash in windows
In windows, you can run the following command at your git repository to store the password and user name at bash.

```bash
git config --global credential.helper wincred
```

This means that the next time you push, you'll enter your username and password as usual, but they'll be saved in windows credential. You won't have to enter them again, after that.

Reference: [Stackoverflow Remember password and user name at bash in windows][1]

[1]: http://stackoverflow.com/questions/5727555/remember-password-git-bash-under-windows
