## Choices

But what is a Visual Novel without choices right?

Choices are built as JSON, with the key "Choice", and every choice available as a sub-item.

Every choice has 2 attributes, the text to display and what to do when it's clicked.

```javascript
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

You can also show some options only if some condition is true.

```javascript
{"Choice":{
    "Developer":{
        "Text": "I'm a developer.",
        "Do": "Developer"
    },
    "Player":{
        "Text": "I'm a Player.",
        "Do": "Player",
        "Condition": "played == true" // This will only be shown if the condition is true.
    }
}}
```

Sometimes you want to show a dialog right with the choices, this is possible adding a text property inside the object:

```javascript
{"Choice":{
    "Dialog": "e Before I continue, let me ask you, what are you?",
    "Developer":{
        "Text": "I'm a developer.",
        "Do": "Developer"
    },
    "Player":{
        "Text": "I'm a Player.",
        "Do": "Player",
        "Condition": "played == true" // This will only be shown if the condition is true.
    }
}}
```

That way the "Dialog" property is the one that will be shown with the choices, as you can see, just like with normal dialogs, you can specify what character is the one talking and take full advantage of other things loke side images on it.