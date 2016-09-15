# The JavaScript Interview Question
##What makes a good coding question in JavaScript and what the candidate's answer says about them.

Everyone who conducts coding interviews has her prefered questions and reasons for asking them. Many will ask general computer science questions such as implementing a sorting algorithm within a certain complexity, others will ask a candidate to write a small application. Personally, I find that the best gage of a candidate's ability to write code at a specific level and to work within a team is to write a simple function and use that as a starting place for a broader conversation.

When choosing a good coding challenge, it is important to cover the basics but allow more advanced candidates a path to solve the challenge in multiple ways. I tend to ask a candidate to write a function, preferably on a computer so that the code can be run in the console of a browser. This allows the candidate to test her work and troubleshoot - both of which are opportunities to learn how the candidate fixes bugs and finds problems. I also try to make sure that the challenge involves loops and conditionals. There are, of course, more advanced topics that can be covered and when testing someone who is obviously more advanced, I will often follow up with questions that involve promises, callbacks, and closures.

Why go so easy on a candidate? Well, the short answer is that I don't like to see people suffer. If I have JavaScript positions for candidates of various experiences, it isn't fair to start off with hard questions and raise the candidate's anxiety level right off the bat. Instead, I find that starting with a simple challenge lets beginners show that they can write working code and I can tell right away when I am dealing with a more advanced programmer and can skip to more challenging questions.

My prefered challenge is known as _FizzBuzz_. It is a fairly well known challenge and there is even a chance that the candidate has done it before, but that is not a reason to not use it. This is one of those questions that can be answered in many ways, and once a candidate has answered the question I like to discuss the thought process that lead to that particular solution. For more advanced programmers, I'll then ask them to try solving it in a couple of different ways and then discuss the differences and why to choose one over the others. Here's how it works:

###FizzBuzz
* Ask the candidate to write a function that outputs the numbers from 1-99 via the console.
* For any numbers that are divisible by 3, output that number with the word "Fizz".
* For any numbers that are divisible by 5, output that number with the word "Buzz".
* For any numbers that are divisible by 15, output that number with the word "FizzBuzz".
* **Also, ask the candidate to write the function as though she is writing code for a project with other developers.**

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
If the candidate has no problem, with this, I'll generally ask her to provide several different ways to write a function (anonymous vs. named vs. arrow) and ask her what the differences between each are. *It is amazing how many people choke just writing a basic function definition.*
####Does the candidate use `'use strict';`
This lets me know whether the candidate has worked on many professional positions, as almost all will require using the statement to enforce consistent interpretation and error handling.
####Can she write a loop?
Ask what are the three parts of the loop definition. If they use `let` or `const`, ask them about block scoping within the loop.
####Does she know what a modulus is?
The use of a modulus in a conditional is not as straight forward as many other operator uses, as it must be evaluated with a comparator. Many candidates will stop at using the operator alone.
####Can she properly order the conditions?
If the candidate uses an `if-else-if-else` construction, are they properly ordered? Checking to see if the number is divisible by 15 as the final condition will never occur in that scenario.
####Does she try to use a single compound ternary?
Many developers will try to be clever and write a single line solution. This works well as a personal challenge, but is not appropriate for a team environment as it is less readable and lacks a justifying performance gain. If the developer chains the ternaries, I will usually discuss these implications on a team to understand the candidates views on the matter.
####Does she use `var`, `let` or `const` and does she understand proper block scoping?
Talk with the candidate about which she used and how to properly use it. If she uses `var`, ask them about ES2015 and when to use `const` and `let`. Also make sure that any `var`'s are placed at the top of the function and ask about "hoisting" in ES5 and lower. 
####Does she know what `console.log` is?
I remember a time when the only way to check the internal state of an application was using `alert`'s. It was a dark, dark time. I was lucky enough to survive those days but many did not. Forunately, the gods gave us the console and the ability to log to it. Oddly, there are still people today who have never heard of it. I'll usually make sure the candidate knows what this is before we begin, and if she doesn't then I will show them how to use it.
####If typed, do they write in a consistent style (spacing, quotes, braces, etc.)?
Most professional development environments will require some sort of linting to correct small syntax errors and enforce a consistent style among the development team. If the code is pretty, I'll comment on that and ask about her experience with linting. If the code is not consistent or uses Allman rather than K & R style, I will ask the candidate about that.

If the candidate struggles with any parts, I'll ask her to walk me through what the function should have in it and in what order. If she types the function on a computer, I'll ask to run the function in the console and examine the output. This is particularly helpful when the candidate has an error, because I can see how she goes about finding and fixing the error.

##Examples
Here are some examples and some things to notice about each:

```javascript
function FizzBuzz() {
  for(i=0;i<99;i++){
    if(i%3===0){
      console.log(i + " Fizz");
    }else if(i%5==0) {
      console.log(i+" Buzz");
    }else if (i%15 == 0) {
      console.log(i+ " FizzBuzz");
    } else {
      console.log(i);
    }
  }
}
```
Things to note:
- `i` is not declared anywhere,
- `i` is going to start at 0 and go to 98,
- inconsistent spacing and lots of cramped areas that are more difficult to read,
- inconsistent use of double- vs triple-equals,
- the conditions are ordered such that if `i` is 15, the condition for `i % 3 === 0` trips instead,
- several logging calls rather than one single call.

```javascript
function FizzBuzz() {
  'use strict';
  var i, out;
  for (i = 1; i < 100; i += 1) {
    out = i;
    if (i % 15 === 0) {
      out += ' FizzBuzz';
    } else if (i % 3 === 0) {
      out += ' Fizz';
    } else if (i % 5 === 0) {
      out += ' Buzz';
    }
    console.log(out);
  }
}
```
Things to note:
- use of `'use strict';` - ask what happens if that isn't there
- properly declared variables using `var` - ask about `let`, `const`, and when/where to use those instead
- use of `+=` rather than `++` - ask about perfomance testing
- use of triple-equals - ask the difference and when to use each

```javascript
const FizzBuzz = () => {
  Array(99).fill().forEach((v, i) => { const j = i + 1; console.log(`${ j }${ j % 15 === 0 ? ' FizzBuzz' : j % 3 === 0 ? ' Fizz' : j % 5 === 0 ? ' Buzz' : '' }`); });
};
```
Things to note:
- this is a "clever" solution that demonstrates some advanced features and several bad practices
  - it uses ES2015 concepts like `const`, arrow functions, and template literals - talk about the candidate's experience with ES2015
  - it attempts to be a one-line solution by not placing blocks on new lines or placing a newline after semicolons - discuss formatting and readability
  - it uses `Array.prototype.fill` which is a handy function but is not supported in IE - discuss array methods and browser compatibility, as well as polyfills

```javascript
const FizzBuzz = function () {
    'use strict';
    let output;
    for (let i = 1; i < 100; i += 1) {
        output = '';
        if (i % 3 === 0) {
            output += 'Fizz';
        }
        if (i % 5 === 0) {
            output += 'Buzz';
        }
        console.log(i + (output ? ' ' + output : ''));
    }
};
```
Things to note:
- use of anonymous function - discuss differences between named and anonymous functions and when to use each
- note the concatenation of conditionals and discuss efficiency (2 tests for `i % 15` rather than 1)

##Conclusions
Whether the candidate writes sloppy or beautiful code, what she uses and why are points of discussion and provide insights into how she views her work and whether she considers how her code is read, understood and used by teammates. I personally find that a simple question like this provides greater insight into how a developer views her role than whether she can compute complexity - that can always be learned later.
