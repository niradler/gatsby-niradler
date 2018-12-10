---
layout: post
draft: false
path: "/posts/react-file-structure/"
tags: 
  - Default
description: "One of the biggest issue for new developer starting to work on an ongoing
project, is the project structure.

let’s test some examples from the wide web and then try to figure out the best
option.

 * This is the default way create react app structur..."
title: "React File Structure"
date: "2018-03-15T11:21:49.000Z"
slug: "/react-file-structure/"
feature_image: /content/images/2018/10/react-file.png
author: "Nir Adler"
---

> One of the biggest issue for new developer starting to work on an ongoing project, is the project structure.

**let’s test some examples from the wide web and then try to figure out the best option.**

*   This is the default way create react app structure

![](https://daveceddia.com/images/cra-1.0-initial-folder.png)

_The problem here is very easily noticed in the src folder will have 100 + file and it will be hard to navigate between relevant files and debug properly._

*   Json like file structure

![](https://www.fullstackreact.com/assets/images/series/react-daily-ui/008/filestructure.png)

There is 2 main issues with this option:

1.  where to store shared component.
2.  deep file nesting.

*   most common way lowercase folders for components , screens/containers , stores, assets

![](https://daveceddia.com/images/suggested-structure.png)

for small to medium site this will be perfectly fine, but when you starting to scale you will face same issues like the previews examples.

> Conclusion: as expected i will recommend on the last option with addition:
> 
> 1.  folder for every component or screen.
> 2.  component dedicate for one screen can be inside a components folder inside screen folder

TIP: every developer need to maintain his developing environment with tools that make his work fast and efficient! example in our case, a cli to create new component:  [**create-react-component-folder**](https://github.com/snaerth/create-react-component-folder)

Look on my [pull request](https://github.com/snaerth/create-react-component-folder/pull/3) for improvement.
    