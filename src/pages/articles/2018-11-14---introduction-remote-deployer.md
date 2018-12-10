---
layout: post
draft: false
path: "/posts/introduction-remote-deployer/"
tags: 
  - aws
  - npm
  - Nodejs
  - deploy
  - deployment
  - tool
description: "New package remote-deployer stable and include core features, to make deployment process much more easier and safer. "
title: "Introduction to my new tool remote-deployer."
date: "2018-11-14T20:47:41.000Z"
slug: "/introduction-remote-deployer/"
feature_image: /content/images/2018/11/deployer-2.PNG
author: "Nir Adler"
---

New package [remote-deployer](https://www.npmjs.com/package/remote-deployer) include core features to make deployment process much more easier and safer.

The idea to create the package, came when I tried to set up CI/CD with gitlab worker to my new project ([devresources](https://devresources.site/)).

The worker has stages like test, build, and deploy. Deployer is used in the deploy stage, after test and build, fire an event to update, the server, a script on the server will pull from git and build the new version.

Deploy with deployer is intuitive and you can use http/ssh and soon ftp method to deploy to a remote server (like aws ec2 server), let's give it a try.

    npm i -g remote-deployer && deployer
    

![](/content/images/2018/11/deployer-1.PNG)

First let's decide on the way we going to use deployer, deployer as for today have 2 ways to deploy ssh/http.

HTTP:

This method is for installing on the server, this is the easier  way, all we doing is to send and forget, easy way to trigger to deploy.

    cd ./project_directory
    deployer init
    

Deployer will start the initialise process.

    A git repository was not found!
    ? Should we create one for you ? No
    ? Pick deploy method: HTTP
    

After complete the process let's fire up the deployment server.

    deployer http start
    

pm2 will fire up the server. (by the way make sure pm2 is installed, npm i -g pm2).

Now to deploy you can simply create a get call to your server ip and the port you configure, make sure to open the port in the network setting or firewall.

This is an example of how the call will look like

    curl http://server-ip:5454/deploy?appKey=bbd120510e451a5e89cb5b829e336f771k12ba79
    

Thas it! very easy, in the end of the article i will show a deployment script example.

SSH:

This method is for installing on the client (developer computer or build server), this is the more advance, secure and flexible way, basically we running a local script on the remote machine, with this way it is very easy to edit deploy script and get the output of the deployment.

    cd ./project_directory
    deployer init
    

Deployer will start the initialise process.

    A git repository was not found!
    ? Should we create one for you ? No
    ? Pick deploy method: SSH```

After complete the process let's fire up the deployment script.

    deployer ssh deploy
    

Deployer will connect to the server by secure connection over ssl, and run the commands from the script line by line.

This is an example of how the call will look like

    #!/bin/bash
    
    cd ~/app/project_directory
    
    git pull --force
    
    docker-compose -f "docker-compose.yml" down
    docker-compose -f "docker-compose.yml" up -d --build
    docker logs project-client_1
    docker logs project-server_1
    
    echo "FINISHED DEPLOYMENT!" 
    

*   don't forget to use the help command  like, deployer -h , deployer ssh -h

Example  of configuration file for gitlab worker .gitlab-ci.yml .

    image: node:alpine
    
    before_script:
      -  apk update && apk add curl
    
    stages:
      - test-server
      - build-client
      - deploy
    
    test-server:
      stage: test-server
      script:
        - cd ./server
        - npm install
        - npm run test
    
    build-client:
      stage: build-client
      script:
        - cd ./client
        - npm i
        - npm run test
        - npm run build
    
    deploy:
      stage: deploy
      script:
        - curl http://server-ip:5454/deploy?appKey=bkd100530d411a5e19cb5b829e336f7710e3ba71
    
        
    

Visit the project on [github](https://github.com/niradler/remote-deployer).
    