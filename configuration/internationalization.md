## Internationalization

You can create a multi-language Game also pretty easily. To do so you need to do 4 simple things:

1. Go to the options.js file and change the engine["MultiLanguage"] value to true.
2. Change your script.

The default Script looks like this:

```javascript
var script = {
    "Start":[
        "Hi, welcome to your first Visual Novel with Monogatari."
    ]
}
```

Your new Multi Language script will have language labels that look like this:
```javascript
var script = {

    "English":{
        "Start":[
            "Hi, welcome to your first Visual Novel with Monogatari."
        ]
    },
    "Español":{
        "Start":[
            "Hola, bienvenido a tu primer Novela Visual con Monogatari."
        ]
    }
}
```

3. Add translations to the strings.js file for your Interface.
4. Finally, add your language options to the select element in the settings page of your HTML.

```markup
<select data-action="set-language">
    <option value="English">English</option>
    <option value="Español">Español</option>
</select>
```

The value attribute of each option has to match the language labels available.
You can write on pretty much every language available for the web, so there's no limitation!
