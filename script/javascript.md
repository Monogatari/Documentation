# JavaScript

Even though you can put more Javascript code in the main.js file and do a lot of things there, sometimes we want to do something in some part of our game. This is why you can also put some Javascript inside your game's script and you have a simple and pro way to do it.

The simple one, is using the $ command:

The syntax is pretty easy: "$ \[Javascript Code\]". Here are some examples:

```javascript
// All variables must be declared as a window property. var x = 0; will not work as expected.
"$ var window.x = 0",
"$ x+=1",
"$ alert(x)"
```

The "pro" way is with functions. Yes, you can put a function inside and it will run it!

To control the flow of your game, you can make the function return either true \(Will immediately execute the next statement.\) or false \(Will wait until the user clicks again.\)

Example:

```javascript
"Hi there!",
function(){
    alert("This is pretty useful!");
    return true; // Will make the engine execute the next statement when the function finishes.
},
"Isn't it?"
```

You can as well use variables in your script.

```javascript
"The result of 2+2 is: " + (2+2),
"Isn't that right?"
```

