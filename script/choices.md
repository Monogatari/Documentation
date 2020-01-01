# Choices

But what is a Visual Novel without choices right?

Choices are built as JSONs, with the key 'Choice', and every choice available as a sub-item.

Every choice requires 2 properties: the text to display and what to do when it's clicked.

```
{"Choice":{
    "Developer":{
        "Text": "I'm a developer.",
        "Do": "jump Developer"
    },
    "Writer":{
        "Text": "I'm a writer.",
        "Do": "jump Writer"
    },
    "Artist":{
        "Text": "I'm an artist.",
        "Do": "jump Artist"
    },
    "Player":{
        "Text": "I'm a Player.",
        "Do": "jump Player"
    }
}}
```

## Conditional Choices

There are some cases where you would only want to show a choice if certain conditions are met. Conditional choices are possible by adding a simple 'Condition' function.

For this example, let's assume this is your `storage` variable:

```
"use strict";
// Persistent Storage Variable

let storage = {
    played: false
};
```

As you can see, we added a 'played' variable inside the storage and set its default to `false`. Now, let's see what would happen with the following Choices:

```
{"Choice":{
    "Developer":{
        "Text": "I'm a developer.",
        "Do": "Developer"
    },
    "Player":{ 
        "Text": "I'm a Player.",
        "Do": "Player",
        "Condition": function () {
            return storage.played == true; // The "Player" option will only be shown if this returns true.
        } 
    }
}}
```

`'Player'` will only be shown if the `'played'` variable we added is `true`, since we defined it as `false`, then it won't be shown however, if somewhere along the script we were to change that variable to `true` then this choice will be shown.

## Showing Text when Showing the Choices

You might want to show a dialog along with the choices, this is possible adding a text property inside the object:

```
{"Choice":{
    "Dialog": "e Before I continue, let me ask you, what are you?",
    "Developer":{
        "Text": "I'm a developer.",
        "Do": "Developer"
    },
    "Player":{
        "Text": "I'm a Player.",
        "Do": "Player",
        "Condition": function () {
            return storage.played == true; // The "Player" option will only be shown if this returns true.
        } 
    }
}}
```

That way the `'Dialog'` property is the one that will be shown with the choices, as you can see, just like with normal dialogs, you can specify what character is the one talking and take full advantage of other things like side images on it.

## Styling your Buttons

The `'Class'` property allows you to give a CSS class to your buttons for special styles. Suppose you had the following CSS in your `main.css` file:

```
.boldedText {
    font-weight: bold;
}
.italicText {
    font-style: italic;
}
```

The `boldedText` and `italicText` classes can then be applied to your buttons by setting their `'Class'` properties in your script, like so:

```
{"Choice":{
    "FirstOption":{
        "Text": "Yes",
        "Do": "jump label1",
        "Class": "boldedText" //A css class to apply to the button.
},
    "SecondOption":{
        "Text": "No",
        "Do": "jump label2",
        "Class": "italicText"
    }
}},
```

This way, the `'Yes'` button will have its text **bolded** and the `'No'` button will have its text _italicized_. You can also use CSS styling to do things like give buttons background images and make the text on them invisible, so you can have buttons with pictures!

