# Characters

Declaring characters is really simple!

First, you need an identifier, this is what you'll use for the 'Say' and 'Show' commands. We'll choose the identifier 'e' for this tutorial.

```javascript
monogatari.characters ({
    'e': {

    }
});
```

Each character has many properties, like the name that is shown to the player, and the color for it.

```javascript
monogatari.characters ({
    'e': {
        name: 'Evelyn', // The name that will be shown when this character speaks.
        color: '#00bfff' // It could also be an rgb or rgba value.
    }
});
```

Since we are building visual novels, we also need images for our characters! You need the Directory inside the img directory where your files will be placed, and assign a simple identifier to each file.

```javascript
monogatari.characters ({
    'e': {
        name: 'Evelyn',
        color: '#00bfff', 
        directory: 'Evelyn', // Optional*
        sprites :{ // Images Identifier for the 'Show' statement.
            'Normal': 'normal.png',
            'Mad': 'hmph!.png',
            'Doubt': 'uhh.png',
            'Disappointed':'ngggg....png',
            'Happy': 'hehehehe.png'
        },
        default_expression: 'face.png', // Optional, side image to show every time the character speaks.
        expressions: { // Side images identifiers to show on dialogs
             'Smiling': 'smiling.png'
        }
    }
});
```

The directory attribute is a subdirectory of characters where the images will be pulled, if no Directory is given, it will be assumed to be the characters directory itself.

