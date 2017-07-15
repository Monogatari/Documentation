## Text

### Show Text

The say statement is used... well, for a character to say something. The syntax is as follows:

"[Character Identifier] [Text to Say]"

```javascript
"e Hi! My name is Evelyn."
```

It also accepts HTML, so you can show many things in a text like the Font Awesome icons.

```javascript
"e The <span class='fa fa-arrow-left'></span> button is the back button, press it to return to a previous state of the game.",
```

If no character identifier is given, it will be considered as a narration and no name will be shown.

```javascript
"This would be a narrator."
```

### Clear the Text
You may want in some point to clear/remove the text. There's a "clear command" for that.
```javascript
"clear"
```

### Side Images
If you've defined the "Side" property for your characters, adding a list of images to show, you can use them as side images with each dialog, to do so, you should use a format like this one:

```javascript
"e:Smiling Hi! My name is Evelyn."
```

This assumes you have a Side image called Smiling, which means with every dialog you can specify what side image to use. If you add the "Face" property then that image will be shown with every dialog without the need of specifying it inside the statement.