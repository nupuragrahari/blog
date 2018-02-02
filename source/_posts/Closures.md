---
title: Closures
catalog: true
date: 2018-02-03 00:17:23
subtitle:
header-img:
tags:
- javascript
- closures
- lexical scoping
---
So, today was one of those days for me when you finally get that moment of clarity about an important concept. Initially, when i began my journey as a javascript developer i came across the concept of closures. I searched around, read blogs, saw tutorials until i believed that i have sufficiently understood the topic. So, after i understood the concept of lexical scopes and global scopes and how closures are related with them, I settled on this description of a closure more or less.

A closure is a function that has access to its own lexical scope, the variables of the outer function and the global variables.

Turns out there is more to that. A closure isn’t simply the function itself but the environment in which it was created also carries equal importance. So, an actual definition of a closure would look something like this.

A closure is the function and the lexical environment combined together, within which that function was declared. This environment consists of any local variables that were in-scope at the time the closure was created.

Let us look at this example to understand better.

        function movieName(firstWord) {
          return function(secondWord) {
            return firstWord + “ ” + secondWord;
          };
        }

        var makeMovieName = movieName(“Justice”);

        console.log(makeMovieName(“League”)); //Justice League

In this example, “Justice” is passed as an argument to the function movieName. The variable makeMovieName is assigned the anonymous function returned by the movieName function.
Now, when makeMovieName is called it remembers the firstWord argument and adds it to the argument passed to it, i.e, “League”. This example shows how the closure keeps the context of the lexical environment in which it was created,
even after the outside function has returned.
It is also important to understand that it is unwise to use closures when not needed for a particular task, since it increases processing speed as well as memory consumption for the particular script.
