# Internationalization

## Translating your Script

You can create a multi-language Game also pretty easily. To do so you need to do 4 simple things:

Go to the `options.js` file and change the `'MultiLanguage'` value to `true`.

By default it looks something like this:

```
monogatari.script ({
    'Start':[
        'Hi, welcome to your first Visual Novel with Monogatari.'
    ]
});
```

Your new _Multi Language_ script will have language labels that look like this:

```
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

## Translating the Engine UI

If you need it, you can define new UI translations as follows:

```
monogatari.translation ('YourLanguage', {
    'SomeString': 'Your Translation'
});
```

A new Language select will be added to the Settings screen showing all the languages your game has available!

The value attribute of each option has to match the language labels available. You can write on pretty much every language available for the web, so there's no limitation!

