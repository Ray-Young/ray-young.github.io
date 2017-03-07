---
layout: post
date: 2017-03-02
title: Andoird Screen Rotation
comments: true
tags: [Android]
---

### Introduction
Basically (If we do not add any code), if we rotate the screen, the
previous activity will be automatically destroyed and the system will
adjust the screen automatically.

Of course, we want do more. Then we have this blog.

It will introduce you how to build another layout for landscape (or
portrait), how to tell the code not to destroy the previous activity,
and how to specify what to do after rotation.

Here we discuss onConfigChange
