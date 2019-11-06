# Split Files

You may want to split your game in more files, and you can do so in a very easy way. Just create another javascript file, and if for example you want to put a label in there, just declare it like this:

```
script["NewLabel"] = {
    "Statements..."
}
```

In case of Multi Language Games:

```
script["Language"]["NewLabel"] = {
    "Statements..."
}
```

The same can be done with music, scenes, characters etc. just remember to import that file in the HTML as well and always before the options.js and monogatari.js files.

