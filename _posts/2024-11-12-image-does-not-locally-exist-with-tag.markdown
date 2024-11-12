---
layout: post
title:  "The push refers to repository.An image does not exist locally with the tag"
date:   2024-11-12 04:00:32 +0000
categories: docker, dockerhub
---

I had just created a docker image and was ready to push it to my repo on docker hub. But I got the following error:

```
The push refers to repository...
An image does not exist locally with the tag..
```

In order to push to docker hub, I need to use the name of my repo as the name for my image, username included.

What I had:

```
Name: docker-image-name 
Command: docker push username/image-name
```
What it should have been and evenutally made it work:

```
Name: Username/docker-image-name
Command: docker push username/image-name
```

The command was correct, but my image name was not. Basically if I want to push docker images to my docker hub, I need to make sure my docker image names match my docker hub repo path.

