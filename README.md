# WCI-1
Source code for the book "Writing Compilers &amp; Interpreters" 1st Edition by Ronald Mak updated to build on modern systems

Originally published in 1991, the code that accompanies this book is quite old and many reviews on Amazon for the book have complained bitterly about the code. 
The original code was written in what the author calls 'classic C', which from what I can tell basically means before ANSI. My hope is that others who may find
themselves working through this book will find this helpful as the printed code in the book is *very* small, in fact, I had to use a magnifying glass to read it!

Because I wanted to make this as cross-platform as possible, I decided to use CMake for organizing the projects. I am still quite new to CMake so my structure may
not be ideal, but as long as it remains useful to other programmers then I'll be happy. I used the C89/90 standard to build the sample code and so far seems to be 
working with minor changes. The largest issue that I've found so far is that I've had to include additional header files, namely <stdlib.h> and <string.h> in many 
of the source files to get them to compile. I have also included a launch.json file for Visual Studio Code, which has been my editor of choice for this project.
I have added debug targets for each executable program in the book along with supplying any runtime parameters they require (usually some sort of source file). 

The ultimate goal is for anyone with VS Code, CMake and a C compiler to be able to pull this down and run with it. Do keep in mind that there are some glaring problems
with the original code that I have not addressed since it would require refactoring and I only wanted to make the changes necessary to get it up and running. I did add
comments in places that are especially egregious or that caused me issues. As a result, I have not been able to remove all compiler warnings. 

NOTE: As of this writing, I am currently on chapter 6. I will be pushing updates periodically as I work through the book.




