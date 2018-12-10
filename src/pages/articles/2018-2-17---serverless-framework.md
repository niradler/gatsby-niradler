---
layout: post
draft: false
path: "/posts/serverless-framework/"
tags: 
  - aws
  - lambda
  - serverless
description: "Serverless [https://serverless.com/]  is your toolkit for deploying and
operating serverless architectures. Focus on your application, not your
infrastructure.

Serverless framework making it a breeze to use cloud function, like google cloud
function..."
title: "Serverless framework"
date: "2018-02-17T02:34:57.000Z"
slug: "/serverless-framework/"
feature_image: null
author: "Nir Adler"
---

> [Serverless](https://serverless.com/) is your toolkit for deploying and operating serverless architectures. Focus on your application, not your infrastructure.

Serverless framework making it a breeze to use cloud function, like google cloud function or aws lambda function, im personally using lambda function and i was amazed how brelinet I felt about the idea after my first lambda function.

The configuration for this kind of function can be hard and often confusing! to solve that, Serverless framework created, to develop a cloud function easily and make it more intuitive. the framework use yml function just like docker.

\*\*Usage \*\*

1.  configure aws-cli account (aws configure).
2.  npm i -g serverless.
3.  to create a new function with babel transpiler, offline support and local env variable file, use serverless install --url [https://github.com/niradler/serverless-nodejs-starter/tree/dev](https://github.com/niradler/serverless-nodejs-starter/tree/dev) --name my-project
4.  cd my-project.
5.  create env.yml (optional).
6.  serverless.yml is the configuration file.
7.  check out the hello function in the handler.js this is the application root file. exportconsthello\=async (event, context, callback) \=> { constresponse\= { statusCode:200, body:JSON.stringify({ message:`</span>Go Serverless v1.0! <span class="pl-s1"><span class="pl-pse">${</span>(<span class="pl-k">await</span><span class="pl-en">message</span>({ time<span class="pl-k">:</span><span class="pl-c1">1</span>, copy<span class="pl-k">:</span><span class="pl-pds">'</span>Your function executed successfully!<span class="pl-pds">'</span>}))<span class="pl-pse">}</span></span><span class="pl-pds">`, input:event, }), }; callback(null, response); }; constmessage\= ({ time, ...rest }) \=>newPromise((resolve, reject) \=>setTimeout(() \=> { resolve(`</span><span class="pl-s1"><span class="pl-pse">${</span><span class="pl-smi">rest</span>.<span class="pl-smi">copy</span><span class="pl-pse">}</span></span> (with a delay)<span class="pl-pds">`); }, time \*1000) );
8.  to run the function locally use, serverless offline start
9.  to deploy just use serverless deploy

> Simple as that! serverless architecture is getting very popular you should not miss it, this is definitely the future!
    