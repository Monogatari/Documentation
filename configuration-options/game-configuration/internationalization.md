---
description: Making Monogatari games multilingual.
---

# Internationalization

## Translating your Script

You can create a multi-language game pretty easily. To do so you need to do 4 simple things:

Go to the `options.js` file and change the `'MultiLanguage'` value to `true`.

```javascript
	// Change to true for a MultiLanguage GameScreen.
	'MultiLanguage': true,
```

Next we will be changing the script to support Multi Language games. A single language game's script will look something like this.

```javascript
monogatari.script ({
    'Start':[
        'Hi, welcome to your first Visual Novel with Monogatari.'
    ]
});
```

Your new _Multi Language_ script will have language labels that look like this:

```javascript
monogatari.script ({

    'English':{
        'Start':[
            'Hi, welcome to your first Visual Novel with Monogatari.'
        ]
    },
    'Español':{
        'Start':[
            'Hola, bienvenido a tu primer Novela Visual con Monogatari.'
        ]
    }
});
```

These language labels are are objects that contain script labels. Their names must be one of the supported languages that are available in the list of available translations. A full list of all available translations for your current version can be found in `monogatari._translations`.

![Picture of monogatari.\_translations for version &quot;2.0.0-beta.10&quot;](../../.gitbook/assets/image%20%2816%29.png)

Please note, each individual translation of your game is its own complete game, effectively. They are not modifications of each other, and there is no "default" game. Nothing is stopping you from making two different language versions of the same game entirely different. They don't need to have the same number of strings, and they also don't need to have the same game logic. On that note, if you have a `jump someLabel` to a label that exists in one translation, but does not exist in the language that the player has selected, then they will get an error telling them that `someLabel` does not exist, so be careful when crafting your script!

## Translating the Engine UI for a not-yet-supported language

If you need to translate the game into a language that Monogatari doesn't support, you can define new UI translations as follows:

```javascript
monogatari.translation ('YourLanguage', {
    'SomeString': 'Your Translation'
});
```

A new Language select will be added to the Settings screen showing all the languages your game has available!

The value attribute of each option has to match the language labels available. You can get a complete list of every string to translate for the UI from `monogatari._translations.English` or whatever language you would like to see using your browser's developer console.

![A picture of the developer console displaying all English translation strings for version &quot;2.0.0-beta.10&quot; ](../../.gitbook/assets/image%20%2818%29.png)

