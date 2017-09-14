# Exploration 1: ES6 capabilities
#### Explorer: Joe Wong
#### Pawprint: jlwxz8
#### Date: 9/13/2017

## SOURCES
[Top JavaScript Frameworks and Topics to learn in 2017](https://medium.com/javascript-scene/top-javascript-frameworks-topics-to-learn-in-2017-700a397b711 "Eric Elliot's 2017 guide")

[The making of Fastbook: An HTML5 love story](https://www.sencha.com/blog/the-making-of-fastbook-an-html5-love-story/)

[How to learn ES6](https://medium.com/javascript-scene/how-to-learn-es6-47d9a1ac2620 "Eric Elliot's ES6 guide")

[Build your first ES6 app](https://codelabs.developers.google.com/codelabs/chrome-es2015/index.html?index=..%2F..%2Findex#0 "A tutorial by google")

## CODE
[My Sticky Note App](http://joewong.me/chrome-es2015/)

[My Code](scripts/main.es6.js)

ES6 supports Classes so...
```javascript
function StickyNotesApp() {
...
}
```
becomes:
```javascript
class StickyNotesApp() {
    constructor() {
    ...
    }
...
}
```

ES6 has arrow functions so...
```javascript
// Saves notes on button click.
this.addNoteButton.addEventListener('click', this.saveNote.bind(this));

// Toggle for the button.
this.noteMessageInput.addEventListener('keyup', this.toggleButton.bind(this));
 ```
becomes:
```javascript
// Saves notes on button click.
this.addNoteButton.addEventListener('click', () => this.saveNote());
 
// Toggle for the button.
this.noteMessageInput.addEventListener('keyup', () => this.toggleButton()); 
```
 
ES6 has more than just var...
```javascript
var key = Date.now().toString();
var pi = 2.1415;
```
becomes:
```javascript
let key = Date.now().toString();
const pi = 2.1415;
``` 

Probably the best change was Template Strings and Interpolation:
```javascript
StickyNote.TEMPLATE =
  '<div class="message"></div>' +
  '<div class="date"></div>' +
  '<button class="delete mdl-button mdl-js-button mdl-js-ripple-effect">' +
    'Delete' +
  '</button>';
```
with Template Strings becomes:
```javascript
StickyNote.TEMPLATE = `
  <div class="message"></div>
  <div class="date"></div>
  <button class="delete mdl-button mdl-js-button mdl-js-ripple-effect">
    Delete
  </button>`;
```

```javascript
this.dateElement.textContent = 'Created on ' + month + ' ' + date.getDate();
```
with Interpolation becomes:
```javascript
this.dateElement.textContent = `Created on {month} {date.getDate()}`;
```

ES6 has spread (the ... operator):
```javascript
// Fires when an instance of the element is created.
StickyNote.createdCallback = function() {
  StickyNote.CLASSES.forEach(function(klass) {
    this.classList.add(klass);
  }.bind(this));
```
becomes:
```javascript
// Fires when an instance of the element is created.
createdCallback() {
  this.classList.add(...StickyNote.CLASSES);
```

ES6 also has [Destructuring](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment), [Promises](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise), and [Generators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Generator) but I haven't explored those concepts yet.

## RECAP
So for this exploration, I first used [Top JavaScript Frameworks and Topics to learn in 2017](https://medium.com/javascript-scene/top-javascript-frameworks-topics-to-learn-in-2017-700a397b711 "Eric Elliot's 2017 guide") to sort out the best Javascript frameworks to learn. Going through the article was very informative, but the one thing that caught my attention was how little I knew about Javascript. I started diving deeper and found out that ES6 had many changes that allows for it to remain a top contender in application development languages. I read an article about [Fastbook](https://www.sencha.com/blog/the-making-of-fastbook-an-html5-love-story/) which describes in detail how HTML5 and Javascript was enough to make an incredible app similar to the Facebook app.

Later I found a great [tutorial](https://codelabs.developers.google.com/codelabs/chrome-es2015/index.html?index=..%2F..%2Findex#0 "A tutorial by google") on Google's codelabs that showed the power of some of ES6's new abilities. I actually had to go through the tutorial twice. My first attempt resulted in a broken app full of bugs so I decided to try again from scratch. The tutorial itself does show every change but it may not always be obvious which is what made my first attempt fail. I had to debug with Chrome dev tools and step through the process little by little.