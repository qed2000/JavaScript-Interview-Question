# The JavaScript Interview Question
##What makes a good coding question in JavaScript and what the candidate's answer says about them.

Everyone who conducts coding interviews has his/her prefered questions and reasons for asking them. Many will ask general computer science questions such as implementing a sorting algorithm within a certain complexity, others will ask a candidate to write a small application. Personally, I find that the best gage of a candidate's ability to write code at a specific level and to work within a team is to write a simple function and use that as a starting place for a broader conversation.

When choosing a good coding challenge, it is important to cover the basics but allow more advanced candidates a path to solve the challenge in multiple ways. I tend to ask a candidate to write a function, preferably on a computer so that the code can be run in the console of a browser. This allows the candidate to test his/her work and troubleshoot - both of which are opportunities to learn how the candidate fixes bugs and finds problems. I also try to make sure that the challenge involves loops and conditionals. There are, of course, more advanced topics that can be covered and when testing someone who is obviously more advanced, I will often follow up with questions that involve promises, callbacks, and closures.

Why go so easy on a candidate? Well, the short answer is that I don't like to see people suffer. If I have JavaScript positions for candidates of various experiences, it isn't fair to start off with hard questions and raise the candidate's anxiety level right off the bat. Instead, I find that starting with a simple challenge lets beginners show that they can write working code and I can tell right away when I am dealing with a more advanced programmer and can skip to more challenging questions.

My prefered challenge is known as _FizzBuzz_. It is a fairly well known challenge and there is even a chance that the candidate has done it before, but that is not a reason to not use it. This is one of those questions that can be answered in many ways, and once a candidate has answered the question I like to discuss the thought process that lead to that particular solution. For more advanced programmers, I'll then ask them to try solving it in a couple of different ways and then discuss the differences and why to choose one over the others. Here's how it works:

###FizzBuzz
* Ask the candidate to write a function that outputs the numbers from 1-99 via the console.
* For any numbers that are divisible by 3, output that number with the word "Fizz".
* For any numbers that are divisible by 5, output that number with the word "Buzz".
* For any numbers that are divisible by 15, output that number with the word "FizzBuzz".
* **Also, ask the candidate to write the function as though he/she is writing code for a project with other developers.**

The expected output should look like the following:
```
1
2
3 Fizz
4
5 Buzz
6 Fizz
...
15 FizzBuzz
...
99 Fizz
```

For anyone who has been programming for more than a few months, this should be a very simple task. But for some reason it isn't. In my experience, given these exact instructions, roughly 50% of candidates can't answer it - even those claiming to be senior developers and having come from large, well-known companies. I'd like to think that the candidates aren't lying about their experience and work history, but many probably are. Here are some of the things I look for:

####Can the candidate write a function in JavaScript?
If the candidate has no problem, with this, I'll generally ask him/her to provide several different ways to write a function (anonymous vs. named vs. arrow) and ask him/her what the differences between each are. *It is amazing how many people choke just writing a basic function definition.*
####Does the candidate use 'use strict';
This lets me know whether the candidate has worked on many professional positions, as almost all will require using the statement to enforce consistent interpretation and error handling.
####Can he/she write a loop?
Ask what are the three parts of the loop definition. If they use `let` or `const`, ask them about block scoping within the loop.
####Do they know what a modulus is?
####Can they properly order their conditions? Do they try to use a single compound ternary?
####Do they use var, let or const and do they understand proper block scoping?
Talk with them about which they used and how to properly use it.
####Do they know what console.log is?
####If typed, do they write in a consistent style (spacing, quotes, braces, etc.)?

If they struggle with any parts, I'll ask them to walk me through what the function should have in it and in what order. If they type the function on their computer, I'll ask them to run the function in the console and examine the output. This is particularly helpful when they have an error, because I can see how they go about finding and fixing the error.
