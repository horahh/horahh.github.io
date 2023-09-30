---
title: My Programming Journey
date: 2023-09-27 12:00:00 -0600
categories: [programming,software]
tags: [programming,hardware,software,rust,python]
---

I have always been amazed by building things and making a more complex version of projects, being in my childhood  playing with small wooden block structures trying to make a mechanical structure at the kindergarden or prefering to program a general solution for a mechanical engineering problem at the university rather than just solving it for a single set of values. 

I had always preferred the more challenging elegant solution that take deep understanding of the underlying set of circumstances for general problems rather that quick hacks that take care of the immediate issue at hand.

Each one of the experiences in programming just made me even more interested in abstracting ideas and making them become a reality.
I am interested in systems programming and high performance. I am a firm believer that the high performance and any cool thing that comes to mind must have a really good quality base in order to scale, in order to thrive when having to survive in the wild.

I have learnt a thing or two about programming and engineering in general and I want to share them in this blog, hopefully this will be useful as well as entertaining.

Programming is about tradeoffs, each programming has its strenghts and weaknesses, learning various languages makes you think with different approaches to a problem. In a very shallow approach we can simplify things and say that C values speed over safety and productivity, Python values productivity over speed. Rust values safety and speed but lacks in short term productivity, more on that later.

I want to pick a few of the main languages that I have came across so that gives a context and some idea of where I come from with my view points.

## [LOGO](https://en.wikipedia.org/wiki/Logo_(programming_language))

![LOGO](https://upload.wikimedia.org/wikipedia/commons/thumb/0/09/KochTurtleAnim.gif/300px-KochTurtleAnim.gif)

At the age of 11 my mother took me for a week into a programming course, turns out it was LOGO, I enjoyed the abstraction concepts and having to simulate in your mind what is going to happen to the screen when the little turtle executes the instructions, those were like right 50, up 50, left 50, down 50 and you just draw a square!

I remember to have tried drawing more complex figures like a castle and it was a nightmare, first debug experience!


## [Basic](https://en.wikipedia.org/wiki/BASIC)

![basic](https://upload.wikimedia.org/wikipedia/commons/thumb/7/7b/AtariBASIC.png/300px-AtariBASIC.png)

At high school, I remember to have done some mathematical functions graphs with the basic programming language and also mathematica, it was the intro to programming. One of the first hard bugs to debug was having typed an example variable with a 1 instead of an l and seeing the compiler complaining of undeclared variable which seem to be declared just a line above.

## [C](https://en.wikipedia.org/wiki/C_(programming_language))
![C](https://upload.wikimedia.org/wikipedia/commons/thumb/0/0e/The_C_Programming_Language%2C_First_Edition_Cover.svg/171px-The_C_Programming_Language%2C_First_Edition_Cover.svg.png)

C was the first programming language intruduced to me in high school but really loved when used it a bit more serious in intro to computation at the university, I even spent my whole summer vacations playing with the compiler and making drawings and discovering special library functions.

Still C is as reliable as always, I believe is the best high level language to understand how computers work, it has a simple syntax, simple and efficient libraries, its drawback is the productivity for real work, is expensive to program in C which makes it a language suitable only for very high performance applications given the resource constraints of the system. 

## [Perl](https://en.wikipedia.org/wiki/Python_(programming_language))

![Perl](https://upload.wikimedia.org/wikipedia/en/0/00/Perl-camel-small.png)

I was introduced to Perl at university in an optional course about open source, in which Perl was used to parse text do file tests and small scripts which I found very intuitive to use and powerful. Using it at professional level lead me to realize how inconvenient and limited it was for doing big projects. It is called write only language for a reason.

Perl has allowed amazing things done and still part of the legacy code for a lot of enterprise software but there are better options for starting a project nowadays.

## [Python](https://en.wikipedia.org/wiki/Python_(programming_language))

![python](https://upload.wikimedia.org/wikipedia/commons/c/c3/Python-logo-notext.svg)

I loved the simplicity and cleanliness of the python code, making indenting mandatory and actual part of the syntax was something very novel for me at the time.

Python is relatively old language but has still remaining solid with modern features, simple to use for the newbies yet powerful and elegant for the pros. Its main disadvantage is its performance which has improved significantly in the latest python versions (3.11 at this moment ) but when pure performance is required could benefit from other language like C/CPP/Rust to bind an implementation for the heavy work within a package that can just get imported.

## [Rust](https://www.rust-lang.org/)

![Rust Logo](https://upload.wikimedia.org/wikipedia/commons/d/d5/Rust_programming_language_black_logo.svg)

It is very common for a SW Engineer to deal with memory errors like null pointers, leaking memory modules, applications that write to an array out of bounds, etc, specially stressful while being pressured to meet deadlines, even sometimes having no clue on how to reliably reproduce an issue even worse how the code is suppose to behave. Thats just a tipical scenario, because you end up dealing with code written by others and poorly documented. 

I could not shy being amazed by the Rust promess of not having to deal with memory problems by simply using the language, perhaps a little bit of overstatement, which would better be stated as not having to deal with memory problems at runtime which means pulling these at compile time, so the game turns into understanding what the compiler complains are about and how to properl solve them. But once the code compiles there is little else to be done which is amazing.


## Rust Mindset  

When programming in Rust there are different prefered patterns than for example CPP or simple C, of course while or for loops could be used but not so much in the spirit of the language, better aim to work with iterators. That really changes how the brain processes the actions needed and the workflow.

Rust is a really efficient language that attempts to implement what the call a trifecta, being safe, fast and concurrent, that even went noticed by the linux kernel becoming this year the second language available for use in the linux kernel.

Rust has caught my interest since 2020 and I have dedicated some time to learning it sporadically but being more serious about it in 2023. Hopefully we can explore more about the language with cool projects and share some learnings.

A good article to better understand why Rust is so unique and interesting for modern high optimization problems is [Rust is the Best Language For Data Infra](https://www.arroyo.dev/blog/rust-for-data-infra) written by  Micah Wylde, explaining most Rust strengths in detail, very recomended lecture.

## Why the reference to [Ikigai](https://medium.com/@marenkate/ikigai-and-the-four-ps-how-to-get-paid-enjoy-your-work-solve-problems-and-find-purpose-8c9dc615648f)?

To explain in simple terms Ikigai is the confluence of what you are passionate about, what the world needs and what you can be paid for.

In other words the idea is to make a living based on something which you are passionate about which of course is programming.

![ikigai](https://www.researchgate.net/profile/Daphna-Arbell-Kehila-2/publication/331982903/figure/fig3/AS:740356199038990@1553526081990/IKIGAI-A-Japanese-concept-meaning-A-Reason-for-Living-This-figure.jpg){: width="700" height="400" }
credit: [researchgate.net](https://www.researchgate.net/figure/IKIGAI-A-Japanese-concept-meaning-A-Reason-for-Living-This-figure_fig3_331982903)


## TO BE CONTINUED ...
