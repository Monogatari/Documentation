# Internationalization

You can create a multi-language Game also pretty easily. To do so you need to do 4 simple things:

Go to the options.js file and change the `engine['MultiLanguage']` value to `true`.

Change your script, by default it looks like this:

```javascript
Monogatari.script ({
    'Start':[
        'Hi, welcome to your first Visual Novel with Monogatari.'
    ]
});
```

Your new _Multi Language_ script will have language labels that look like this:

```javascript
Monogatari.script ({

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

If you need it, you can define new UI translations as follows:

```javascript
Monogatari.translation ('YourLanguage', {
    'SomeString': 'Your Translation'
});
```

A new Language select will be added to the Settings screen showing all the languages your game has available!

The value attribute of each option has to match the language labels available. You can write on pretty much every language available for the web, so there's no limitation!

