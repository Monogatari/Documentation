## JavaScript

Even though you can put more Javascript code in the main.js file and do a lot of things there, sometimes we want to do something in some part of our game. This is why you can also put some Javascript inside your game's script. To do it, Monogatari has implemented a simple and advanced methods and you can use any of them depending on your needs:

### The Simple Way

The simple one, is using the $ command:

The syntax is pretty easy: "$ [Javascript Code]". Here are some examples:

```javascript
// All variables must be declared as a window property. var x = 0; will not work as expected.
"$ var window.x = 0",
"$ x+=1",
"$ alert(x)"
```

You can as well use variables in your script, just remember the variables you use must be declared prior it's use.

```javascript
"The result of 2+2 is: " + (2+2),
"Isn't that right?"
```

### The Advanced Way
Now, while that way makes it really simple to do some tasks, there are others that need another approach. The "advanced" way is actually using JavaScript functions. Yes, just like you would on any other JS file, you can use function syntax inside your script.

To control the flow of your game, you can make the function return either true (Will immediately execute the next statement.) or false (Will wait until the user clicks again.)

Example:

```javascript
"Hi there!",
function(){
    alert("This is pretty useful!");
    return true; // Will make the engine execute the next statement when the function finishes.
},
"Isn't it?"
```

While that may be ok for a few functions, as you can see after a while your code starts to become more complicated, a way to simplify things is declaring the functions before your script and then just using the name to call it in the script like this:

```javascript
function sendAlert(){
    alert("This is pretty useful!");
    return true;
}

var script = {
	// The game starts here.
	"Start": [
		"Hello, after this the function will be run.",
        sendAlert, // You can use just the name of the function!
        "Well, that looks a lot better!"
    ]
}
```

Using that technique will make your game a lot more easy to debug and update!

### Async Functions
While the advanced way adds a lot of more possibilities to your game, it still doesn't solve the fact that you may need to realize some async tasks such as a request or other activities. Since v1.3.2, using [JavaScript Promises](https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Global_Objects/Promise) is possible.


```javascript
function asyncFunction(){
	return new Promise((resolve, reject) => {
            // All your code should be here
            setTimeout(function(){
                // You need to resolve the promise once your task is done
                resolve("Success!"); 
            }, 2150);
        }).then((successMessage) => {
            alert( successMessage);
            return true;
    	});
}

var script = {
	// The game starts here.
	"Start": [
		"Hello, after this the function will be run.",
        asyncFunction,
        "Well, that looks a lot better!"
    ]
}
```

Just as with the common functions, if you return a true value from your promise, the next statement will be executed as soon as it's done and will wait if you return anything else. The game will also block on the meantime so the player won't be able to continue until the Promise is resolved.

