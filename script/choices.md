# Choices

But what is a Visual Novel without choices right?

Choices are built as JSON, with the key "Choice", and every choice available as a sub-item.

Every choice has 2 attributes, the text to display and what to do when it's clicked.

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

You can also show some options only if some condition is true.

```
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

