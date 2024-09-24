---
layout: post
title:  "Locating Missing Dockerfile"
date:   2024-09-24 02:52:32 +0000
categories: docker
---

Can't find Dockerfile even though it's there?

I was using VS Code to create dockerfiles and used the common "Dockerfile" name so that I can use the simply "docker build" command. Even though
I didn't specify it, VS Code added a ".dockerfile" extension. So Docker found "Dockerfile.dockerfile" instead of "Dockerfile". 

Using the -f option worked, but also simply removing the .dockerfile extension. Admittedly, took longer than it should have to realize why Docker couldn't find the file...
