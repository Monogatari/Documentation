## Characters

Declaring characters is really simple!

First, you need an identifier, this is what you'll use for the "Say" and "Show" commands. We'll choose the identifier "e" for this tutorial.

```javascript
var characters = {
    "e":{

    }
}
```
Each character has many properties, like the name that is shown to the player, and the color for it.

```javascript
var characters = {
    "e": {
        "Name": "Evelyn", // The name that will be shown when this character speaks.
        "Color": "#00bfff" // It could also be an rgb or rgba value.
    }
}
```
Since we are building visual novels, we also need images for our characters! You need the Directory inside the img directory where your files will be placed, and assign a simple identifier to each file.

```javascript
var characters = {
    "e": {
        "Name": "Evelyn",
        "Color": "#00bfff",
        "Directory": "Evelyn", // Optional*
        "Images":{ // Images Identifier for the "Show" statement.
            "Normal": "normal.png",
            "Mad": "hmph!.png",
            "Doubt": "uhh.png",
            "Disappointed":"ngggg....png",
            "Happy": "hehehehe.png"
        },
        "Face": "face.png", // Optional, side image to show every time the character speaks.
        "Side": { // Side images identifiers to show on dialogs
             "Smiling": "smiling.png"
        }
    }
}
```

* The directory attribute is a subdirectory of characters where the images will be pulled, if no Directory is given, it will be assumed to be the characters directory itself.
