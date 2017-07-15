## Messages

A message is a nice way of showing the user some content. You could also use it as a mailbox or something for your game.

First you need to declare your message, it consists on an Identifier, Title, a A subtitle and the message body.

```javascript
var messages={
    "SampleWriting":{
        "Title": "Some sample writing",
        "Subtitle": "From Evelyn",
        "Message":"Just look how easy it is!&lt;br&gt;&lt;img src='img/sample.png'&gt;"
    },
}
```

As you can see, you can also write HTML on them!

Next, to show them up in your game, yo just need the Display Message command.

```javascript
"display message SampleWriting"
```

Each message has a close button so the user is able to close it when he's finished reading it.
