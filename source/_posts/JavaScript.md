---
title: JavaScript
date: 2016-11-01 18:44:04
tags: js, javascript
---

#### Download the boilerplate:

[Click this link to get the boilerplate files](https://www.dropbox.com/sh/2yw0kchf0s8dstm/AAAK33btqd3glg44M-t_xA0za?dl=1)

- Open the downloaded folder in Atom and look through the files. You'll see some HTML and CSS already set up, and an empty JS file.
- Look through the HTML and CSS for a review, and open the file in Chrome to see what it looks like.
- Open the JS file in the boilerplate you downloaded and write `console.log('Hello world!')` then save it and reload your browser, then open up the chrome dev tools and select "console" from the right pane. You should see your first JavaScript program!

#### JavaScript

##### [Intro to JS](https://slides.com/michaelelliott/intro-to-js)

<iframe src="//slides.com/michaelelliott/intro-to-js/embed" width="580" height="420" scrolling="no" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe>


##### Number guessing game

- Copy this one piece at a time into your JS file. Try to see what each line does, and play around with the game. See what other things you can do with this.

```JavaScript
// I'm a comment!
var answer = Math.ceil(Math.random() * 50);
var form = document.querySelector('form');
var input = document.querySelector('input');
var response = document.querySelector('.response');
var response = $('.response')
console.log(answer);

document.addEventListener('submit', checkGuess);

function checkGuess (event) {
  event.preventDefault();
  var guess = input.value;
  if (guess == answer) {
    response.textContent = guess + " is correct!";
    form.style.backgroundColor = "#27ae60";
  } else if (guess > answer + 10) {
    response.textContent = guess + " is WAY too high!";
    form.style.backgroundColor = "#f39c12";
  } else if (guess > answer) {
    response.textContent = guess + " is too high!";
    form.style.backgroundColor = "#f39c12";
  } else if (guess < answer - 10) {
    response.textContent = guess + " is WAY too low!";
    form.style.backgroundColor = "#f39c12";
  } else if (guess < answer) {
    response.textContent = guess + " is too low!";
    form.style.backgroundColor = "#f39c12";
  } else {
    response.textContent = guess + " is not a number!!!!";
    form.style.backgroundColor = "#c0392b";
  }
}
```

#### Next week

##### [JS Data Structures and Algorithms](https://slides.com/michaelelliott/js-data-algo)

<iframe src="//slides.com/michaelelliott/js-data-algo/embed" width="580" height="420" scrolling="no" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe>


