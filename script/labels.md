## Chapters Called Labels

Labels are just like the book's chapters, they define parts in your game. Take a look at this sample script:

```javascript
var script = {
    "Start":[
        "This is a statement."
    ]
}
```

See that "Start" string? That's how a label is defined. Your game will always start in that "Start" label and every game must have one.

Inside it, you'll see a statement, which are the lines that tell your story and the way you'll do many things.
As labels are as chapters, you can have as many as you want!

```javascript
var script = {
    "Start":[
        "This is a statement.",
        "jump mylabel"
    ],
    "mylabel":[
        "This is another statement.",
        "Pretty easy huh?"
    ]
}
```

See that "jump mylabel"? that's how you can change between labels, the jump statement will take you to the label you give it.
