## Notifications

A notification may be useful to let the user notice something. You could also use it as an achievement system for your game.

First you need to declare your notification, it consists on an Identifier, Title, a A subtitle and the message body.

```javascript
var notifications = {
    "SampleNotification":{
        title: "Hey!",
        body: "This is a notification",
        icon: "img/logo.png"
    },
}
```

Next, to show them up in your game, yo just need the notify command.

```javascript
"notify SampleNotification"
```

If you want your notification to hide after a while, you can tell after how many miliseconds it should go away:
```javascript
"notify SampleNotification 300"
```

That way, the notification will pop up and then go away after the 300 miliseconds have passed.
