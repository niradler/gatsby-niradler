---
layout: post
draft: false
path: "/posts/building-node-js-module-validate-tracking-number/"
tags: 
  - Default
description: "After a quick search I didn’t find any nodejs solution to validate tracking
number, it was easy decision to just build one!

getting started:

 * clone this template [https://github.com/cleverbeagle/npm-package-template] 
   so we can use es6+
 * cd ..."
title: "Missing nodejs module ? building node js module to validate tracking number"
date: "2018-02-14T00:14:06.000Z"
slug: "/building-node-js-module-validate-tracking-number/"
feature_image: null
author: "Nir Adler"
---

> After a quick search I didn’t find any nodejs solution to validate tracking number, it was easy decision to just build one!

**getting started:**

*   clone this [template](https://github.com/cleverbeagle/npm-package-template) so we can use es6+
*   cd folder && npm i
*   we will add the code to the src folder

> How to validate tracking number ? a quick search return regex format for the big couriers.

\*\*File structure: \*\*

\- config -> store the regex format for each courier - helpers -> functions: getCourier, isValid - dist -> client code - main index.js

> for best practice I tried to write modular

\*\*getCourier\*\*

getCourier(tr) { for (const key in courier\_info) { const courier = courier\_info\[key\] if (courier.test(tr)) { return key; } } return null; }

\*\*isValid\*\*

isValid(tr, type) { for (const key in courier\_info) { const courier = courier\_info\[key\] if (courier.test(tr) && key === type.toLowerCase()) { return true; } } return false; }

> Final steps:
> 
> add some examples ([demo](https://niradler.github.io/tracking-number-validation/))
> 
> edit readme file and fill the details of the package in the package.json
> 
> run yarn build && npm publish

check it out \[GITHUB \](https://github.com/niradler/tracking-number-validation) \[NPM\](https://www.npmjs.com/package/tracking-number-validation)
    