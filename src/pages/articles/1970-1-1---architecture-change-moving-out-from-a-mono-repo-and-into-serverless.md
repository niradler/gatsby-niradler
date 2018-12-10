---
layout: post
draft: false
path: "/posts/architecture-change-moving-out-from-a-mono-repo-and-into-serverless/"
tags: 
  - Default
description: "As part of the aws  solutions architect exam and my devops training I'm
constantly changing stacks, I use my personal project (devresources
[https://devresources.site]) as architecture example.

I have a small machine on aws, a light sail  3.5$ entra..."
title: "Architecture change - moving out from a mono repo and into serverless"
date: "1970-01-01T00:00:00.000Z"
slug: "/architecture-change-moving-out-from-a-mono-repo-and-into-serverless/"
feature_image: null
author: "Nir Adler"
---

As part of the aws  solutions architect exam and my devops training I'm constantly changing stacks, I use my personal project ([devresources](https://devresources.site)) as architecture example.

I have a small machine on aws, a light sail  3.5$ entrance, my stack is fully developed and deploy on docker using docker compose with nginix for client express server Mongodb and express data collector, docker compose example. Docker file.

I setup ci/CD with gitlab and gitlab worker and deployer tool.

The new stack is much cheaper 0.0$ cost s3 for client hosting a lambda function as the server and ec2 for dB, I also using hosted zone for the domain handling, for cdn and free ssl for the client I'm using cloud flare, I use the aws certificate manager for ssl for the aws domain handling part.

Lambda develop with serverless framework.

Serverless plugins Tip:learn cloud formation

Distribute repos
    