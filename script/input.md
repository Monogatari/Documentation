## Accepting user Input

There are many cases where we need input from the user, like to ask their name. There is an input statement for this.

This is a sample script with an input statement:


```javascript
var script = {
    // The game starts here.
    "Start": [
        "You'll see an input next",
        {"Input": {
            "Text": "What is your name?",
            "Validation": function(input) {
                return input.trim().length > 0;
            },
            "Save": function(input) {
                storage.player.Name = input;
            },
            "Warning": "You must enter a name!"
            }
        },

        "Hi {{player.Name}} Welcome to Monogatari!"
    ]
}
```

As you can see, the input statement is in fact an object, with 4 properties, Text, Validation, Save and Warning.

### Text

The text to be displayed in the input dialog

### Validation

The validation function, there are times when you want to validate the user input, to see if it's not empty for example, the Validation property should be a function returning a boolean, the validation process is up to what you want.

### Save

The save function, what Monogatari will do with the input once it's validated, normally you would save it on storage, but you can do whatever you want with it, the save property is then a function that receives the input, what you do with it is also uo to you.

### Warning

The warning property is just the message that will be shown in case the input fails the validation, something useful for the player to know what you expect from them.
