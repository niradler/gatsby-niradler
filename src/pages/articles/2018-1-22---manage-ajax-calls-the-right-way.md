---
layout: post
draft: false
path: "/posts/manage-ajax-calls-the-right-way/"
tags: 
  - Default
description: "Today i will try to represent you a small npm package that i wrote to help me
keep my ajax call managed, and be prepared for the next project.



Every time I get to the part of connecting my client to a server, I try to group
my ajax calls in one pl..."
title: "Manage AJAX calls the RIGHT way!"
date: "2018-01-21T23:02:54.000Z"
slug: "/manage-ajax-calls-the-right-way/"
feature_image: null
author: "Nir Adler"
---

> Today i will try to represent you a small npm package that i wrote to help me keep my ajax call managed, and be prepared for the next project.

Every time I get to the part of connecting my client to a server, I try to group my ajax calls in one place to keep it manageable,

Also to adapt fast to changes i lately use a config file to create a flexible environment.

My solution look like that:

const config = { url: '[https://book-store-adonis.herokuapp.com/api](https://book-store-adonis.herokuapp.com/api)', actions: { get:{ method: 'GET', path: '/book/:id' } } }

class Server { constructor(config) { this.config = config } get(id) { return axios({ method: this.config.actions\['get'\].method, url: this.config.url.concat(this.config.actions\['get'\].path).replace(':id',id), }); } }

After using this method couple of times I decided to create an npm module to help me in my next project.

keep in mind that npm package still has to be written in es5.

This is how my package look like.

if (typeof require === 'undefined') { if (!axios) { console.log('axios is a dependency, please include it in the top of the index.html file ()') } } else { var axios = require('axios'); } function Server(config) { this.url = config.url; this.actions = config.actions; for (const key in this.actions) { Server.prototype\[key\] = function(param,data) { var host = this.url.concat(this.actions\[key\].path); var find\_var = host.indexOf(':'); if (find\_var>-1 && arguments.length>0) { for (var i = 0; i < arguments.length; i++) { var name=Object.getOwnPropertyNames(arguments\[i\])\[0\], value=arguments\[i\]\[name\]; host = host.replace(':' + name,value) } } var options ={ method: this.actions\[key\].method, url: host, } if(\['post','put'\].indexOf(this.actions\[key\].method.toLowerCase())>-1) options.data=data?data:{}; return axios(options); } } } if (typeof exports === 'undefined') { window.Server=Server; } else { module.exports= Server; }

Now let’s try to break it down.

if (typeof require === 'undefined') { if (!axios) { console.log('axios is a dependency, please include it in the top of the index.html file ()') } } else { var axios = require('axios'); }

In order to provide flexibility between node and browser environment, checking  for axios (HTTP library) in both options.

function Server(config) { this.url = config.url; this.actions = config.actions; for (const key in this.actions) { Server.prototype\[key\] = function(param,data) { var host = this.url.concat(this.actions\[key\].path); var find\_var = host.indexOf(':'); if (find\_var>-1 && arguments.length>0) { for (var i = 0; i < arguments.length; i++) { var name=Object.getOwnPropertyNames(arguments\[i\])\[0\], value=arguments\[i\]\[name\]; host = host.replace(':' + name,value) } } var options ={ method: this.actions\[key\].method, url: host, } if(\['post','put'\].indexOf(this.actions\[key\].method.toLowerCase())>-1) options.data=data?data:{}; return axios(options); } } }

> for people aren’t familiar with oop in js, try to imagine function = class, and the code above is the constructor of this class.

After configuring the variable in our function, im creating the function according the actions in the config file (like “get” above),

All the functions is actually the same there is 2 factors that changes:

1.  If there is param we need to replace (like /:id in out “get” example).
2.  Add data option for post and put method.

Pretty simple code, but acting this way will help you create client server bridge that you can maintain easily, for example try to think what happens if you pull the config from the server itself.

link to try it out [https://www.npmjs.com/package/server-mapping](https://www.npmjs.com/package/server-mapping)
    