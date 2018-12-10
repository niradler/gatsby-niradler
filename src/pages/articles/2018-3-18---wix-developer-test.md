---
layout: post
draft: false
path: "/posts/wix-developer-test/"
tags: 
  - Default
description: "This is a simple 2 step test for wix.com

 * link for the test site [https://www.wix.com/wix-lp/software-engineers] press
   F12 to start (open dev tools)
 * And this is what you going to see:

Hi, you made it! 👋 You are about to face a few puzzles ..."
title: "WIX developer test"
date: "2018-03-18T19:16:50.000Z"
slug: "/wix-developer-test/"
feature_image: /content/images/2018/10/wix.png
author: "Nir Adler"
---

**This is a simple 2 step test for wix.com**

*   [link for the test site](https://www.wix.com/wix-lp/software-engineers) press F12 to start (open dev tools)
*   And this is what you going to see:

Hi, you made it! 👋 You are about to face a few puzzles that will require some wit and coding skills to solve. The answer to each puzzle is a number, which you'll use in order to progress to the next step. We'd love to see your code so please save it somewhere shareable (e.g. as a private: [https://gist.github.com/](https://gist.github.com/))

When you feel ready just type start in the console and press Enter. Good luck!✌️

*   type “start” and submit (enter)

Ready, set, go! To answer a question simply assign the answer to theanswerparam in the console (e.g. typeanswer = 42 and hit Enter). - #1: Assuming '(' means go up and ')' means go down, which floor will you end up on given the input? The building you are in has an infinite number of floors and an infinite number of basements. You start at floor 0. Your input is: ())))(((()))))() ...

*   after carefully reading the assignment lets start

    // #1 const str1 = `((())))((() ...` let i = 0 ; for (let key of str1) { if(key == '(') i++; else if(key == ')') i--; } console.log('the floor is '+ i)
    

*   like you can see, a simple solution in the form of looping the string and changing the variable (i) that represent the floor.
    
*   let’s continue to the next task (to do so you need to assign the answer like answer = 42 😉
    
*   2: Assuming '<' means left, '>' means right, '^' means up and 'v' means down, you start at a position in the middle of a huge field, where you have more than enough room to move. You start walking according to the directions in input. How many positions did you visit more than once? The position you start in is considered a visit. Your input is: >vv>v>^^
    ====================================================================================================================================================================================================================================================================================================================================================================
    
*   after carefully reading the assignment let’s start working, this task is more complicated let’s start with building the algorithm to solve the task - first we need to decide on the size of the map (the area we move and we can mark places we already visit)
    
*   then we need to initialize the map with zero = no visit and 1 for visit in the middle
    
*   now we need to mark visit area and count when we are visiting a point we already visit (tricky part here is that we need to count only one per position)
    
*   let’s look on the code now
    

    // #2 const str2 = `>^<v>^< ...`; //calc map size const buildMap = ()=>{ let x=0,y=0,max_x=0,max_y=0; const is_max_x = (x)=> Math.abs(x) > max_x ? max_x = Math.abs(x) : false; const is_max_y = (x)=> Math.abs(y) > max_y ? max_y = Math.abs(y) : false; for (let key of str2) { switch (key) { case '<': x-=1; is_max_x(x) break; case '>': x+=1; is_max_x(x) break; case '^': y+=1; is_max_y(y) break; case 'v': y-=1; is_max_y(y) break; default: console.log('ERR!') break; } } //return map size return max_x > max_y ? (max_x *2)+1 : (max_y *2)+1 ; } const markAsVisit = (x,y) =>{ if (map[x][y] == 1) { number_of_visits++; map[x][y] = 2; } else if(map[x][y] == 2){ //ignore } else { map[x][y] = 1; } }; const map = [] const map_size = buildMap(); let x = Math.round(map_size/2)+1,y = Math.round(map_size/2)+1; // set location to center //fill the map for (let i = 0; i < map_size; i++) { map.push([]) for (let j = 0; j < map_size; j++) { map[i].push(0) } } map[x][y] = 1;// visit first let number_of_visits = 0; for (let key of str2) { switch (key) { case '<': x-=1; markAsVisit(x,y) break; case '>': x+=1; markAsVisit(x,y) break; case '^': y+=1; markAsVisit(x,y) break; case 'v': y-=1; markAsVisit(x,y) break; default: console.log('ERR!') break; } } console.log('number_of_visits',number_of_visits)
    

*   try to copy the code and run it step by step, so you can understand how we simplify the task by breaking it to simple pisces and deal with them step by step.

> This was a simple break down of the test, there is many option to solve it, even betters ways for the second task like dynamically change the size of the map etc …
    