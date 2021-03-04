# bitgame-js
bitgame, in javascript

## Abstract

It's a game. You have a byte, meaning eight bits, each of which can be on or off. They can be visually represented however you like - e.g. lightbulbs. You also have five buttons: Increment, Decrement, Left Shift, Right Shift, and Complement. You receive the byte in a certain configuration, and must manipulate it to some other configuration - that is, some other binary number - using just those five unary bit operators, in as few steps as possible.

There are four modes: easy, medium, hard and superhard. On easy, the number you are supposed to reach is given in binary, on medium in hex, on hard in decimal, and on superhard as an ASCII character.

My goal is to eventually expand the game to explore other aspects of low-level programming and computer science in a visually compelling manner.

## Background

I have already implemented a skeleton of the program in Python. In that version, I built the UI with tkinter, which was fine, but I think HTML will be easier. I wrote it at a time when I was still deeply uncomfortable with the idea of OOP. It is split into two files: bitgame_proto, which initializes an array of booleans and then contains a bunch of manipulations to be performed on that array.

The thing I am trying to do is extremely simple, and I have already accomplished it more or less to my satisfaction. But there is still a lot to think about! Here are a few thoughts:

1. The byte should be an object, with the array as a property and then five methods. It seems to me that having a function that acts upon a global variable like that is bad practice.
2. I really like the way the UI is organized. After initializing a window, I first define a function called "update" which brings the colors of the buttons up to date with the current configuration of the bitArray. Then I define a whole list of functions that will be bound to the buttons, each of which is just a bg function (about which more later) and update(). Then I actually make the UI, and finally I call tk.mainloop().
3. The backend, which I called "bitgame_proto", is also pretty good. I decided to represent the byte as a list of eight booleans. For the new version I might want to switch to zeroes - I think that might make for more flexibility. Zero always casts to false, but false doesn't always cast to zero, same with one and true. I should make it a class.

## Next Steps

The first step is to implement what I already have as a website. 