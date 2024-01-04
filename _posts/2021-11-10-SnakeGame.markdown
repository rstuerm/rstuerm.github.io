---
layout: post
title:  "Snake Game"
date:   2021-11-10 13:04:54 -0600
categories:
image: /assets/SnakeGame/Snake.png
---

&nbsp;

This was a quick game I coded in C++. The goal of this project was to code a game in a way that would allow it to be easily recreated using machine code on the 8-Bit CPU I designed. In this sense it served as a more practical way to practice the coding mechanics needed. I have not yet implemented a comparable program on the CPU, but I hope at some time in the future I will get the chance to. 

The game can be played [here (refresh if the game does not load)]({{ site.baseurl }}{% link /Snake.html %}). 

The snake can be controlled with the "up", "down", "left", and "right" arrow keys, and the game can be restarted after a collision by pressing the "return" key. Buttons are also included on the webpage for use on mobile devices without a physical keyboard. Some browsers may not support running the program.

One of the more interesting aspects of the program was the design of a low level random number generator. I used a Lehmer algorithm for this purpose which worked out well. Using this random number generation I was able to account for different grid dimensions automatically by calculating the minimum amount of "randomness" that the algorithm requires for the selected grid dimension. The current world time is used as a starting seed, but on the 8-Bit CPU the contents of memory or a register could be used, which are random on power up.

This code was written entirely in C++ as seen at my [GitHub][GitHub], so in order to get the program to execute in a web browser I used the emscripten toolchain.

[GitHub]: https://github.com/rstuerm/SnakeGame