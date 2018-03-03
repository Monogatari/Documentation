## Wait

What if you would want to wait some seconds before something happening? let's take a look at this script:

```javascript
let script = {
	// The game starts here.
	"Start": [
		"Hello there! I want you to wait 5 seconds now",
        "wait 5000",
        "Wow, that was a long time!",
        "end"
	]
};
```

The `wait` statement allows us to make the game wait for a certain ammount of time before continuing. In this case, the first dialog will be shown, then, when the player continues, the `wait` statement will make it wait for 5 seconds and then the next dialog will be shown.

You may be wondering why it says `5000` instead of just `5` in order to wait 5 seconds, the reason behind it is that the `wait` statement accepts the time in milliseconds, therefore we have to make the convertion from seconds to milliseconds for it to work as we want.