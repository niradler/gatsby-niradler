---
layout: post
draft: false
path: "/posts/how-my-example-npm-package-got-9-5k-downloads/"
tags: 
  - npm
  - JavaScript
description: "In a previous blog post i explained how to start with creating an npm package i
decided to go with a real world example and created a tracking number
validation.

As a developer working in an ecommerce startup (shelfmint
[https://shelfmint.com/]) the..."
title: "How my example npm package got 9.5k+ downloads."
date: "2018-11-03T22:22:02.000Z"
slug: "/how-my-example-npm-package-got-9-5k-downloads/"
feature_image: /content/images/2018/11/screencapture-npmjs-package-tracking-number-validation-2018-10-22-23_02_04.png
author: "Nir Adler"
---

In a previous blog post i explained how to start with creating an npm package i decided to go with a real world example and created a tracking number validation.

As a developer working in an ecommerce startup ([shelfmint](https://shelfmint.com/)) the pain was recognized and the solution was known.

The package i created was very simple but it worked as expected.

After couple of months, while uploading new package to my [npm account](https://www.npmjs.com/~niradler55), I noticed a package with very high amount of downloads. due to the npm design, you can see only downloads of a given month and not the total downloads, to do that, you need to use external tool such as [npm-stats](http://www.npm-stats.com/Niradler55).

So let's think of the what and why the package got this traffic of downloads, and I even have a confirmation that is used in a production environment.

Let's start with the traffic the package got, a very big percentage of that traffic in my opinion, came from the name of the package, tracking-number-validation the name gives you all the information you need to understand exactly what the package does, and if you need to validate tracking number with JavaScript the package will be one of the first options you get in Google, npm, and github. Pretty cool with a very little amount of effort the package is out there and it is very noticeable for a person who actually needs to address the pain of validate tracking numbers, so I think we pretty much understand why we have traffic.

Now to the downloads and the use, as expected when choosing a real pain, there is a lot of people with the same issue that will love to get a simple solution, ready made especially for this, although the package was just a demonstration, it did work and validate tracking numbers.

After the excitement from the first version I actually released a new version with improve api and test coverage.

Check it out [here](https://www.npmjs.com/package/tracking-number-validation) 😇
    