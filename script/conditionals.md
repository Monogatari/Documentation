## Conditionals

Chances are, at some point you'll want to control the flow of your game depending on certain conditions, like jumping to certain labels or even show different dialogs depending on some condition. To do this, Monogatari has Conditional objects, let's take a look at this Conditional taken from the Demo:

```javascript
{"Conditional": {
	"Condition": function(){
		return storage.evelyn_name == "Evelyn";
	},
	"True": "e Evelyn... That's a lovely name! I love it!",
	"False": "e {{evelyn_name}}... Yeah, sounds good!"
}},
```

As you can see, a Conditional is made up of 3 properties, a `"Condition"`, the function that will be used to determine whether the condition is met or not. In these case, we are checking if the variable `storage.evelyn_name` is equal to `"Evelyn"`, if the condition returns `true`, the statement inside the `"True"` property will be run, if it's false then the statement inside the `"False"` property will be run.

In this case, those statements are dialogs so that simply means that if the condition is true, the first dialog will be shown, if not then the second one will be shown.


Of course dialogs is not the only thing we can do here, we can also use Conditionals to jump to certain labels like this:

```javascript
{"Conditional": {
	"Condition": function(){
		return storage.played == true;
	},
	"True": "jump Played",
	"False": "jump NewGame"
}},
```