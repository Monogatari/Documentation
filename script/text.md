# Text

#### Show Text

The say statement is used... well, for a character to say something. The syntax is as follows:

"\[Character Identifier\] \[Text to Say\]"

```javascript
"e Hi! My name is Evelyn."
```

It also accepts HTML, so you can show many things in a text like the Font Awesome icons.

```javascript
"e The &lt;span class='fa fa-arrow-left'&gt;&lt;/span&gt; button is the back button, press it to return to a previous state of the game.",
```

If no character identifier is given, it will be considered as a narration and no name will be shown.

```javascript
"This would be a narrator."
```

#### Clear the Text

You may want in some point to clear/remove the text. There's a "clear command" for that.

```javascript
"clear"
```

