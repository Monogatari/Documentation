## Images

The show statement is used to show a character or an Image. The syntax is as follows:

In case of characters: **"show [Character Identifier] [Image Key] [position] with [Animation]"**

In case of Images: **"show [Image Identifier or File] [position] with [Animation]"**

Every position is a CSS class, so you can declare your own! The ones available by default are: center, left and right. Take a look at more css classes in the "Designing my Game" section, you can also declare your own.

### Showing Characters

Remember every character image must be declared in the character.

```javascript
"show e normal center with fadeIn",
```

The [animation](https://daneden.github.io/animate.css/) is completely optional, and if a position is not given, it will show in the center by default.

```javascript
"show e normal",
"show e normal with fadeIn",
```

To hide a character, you only need the "hide" command. Syntax: "hide [Character Identifier] with [Animation]"

```javascript
"hide e"
```

You can also hide them with one of the [exit animations](https://daneden.github.io/animate.css/) available.

```javascript
"hide e with fadeOut"
```

All Characters images must be inside the characters subdirectory of img.

### Showing Images

In case of images, they can be declared to use an identifier or you can also use the file's name. The root directory for images will always be img.

```javascript
"show flower center with fadeIn", // If flower is declared
"show flower.png center with fadeIn" // If flower isn't declared
```

To hide this images, you'll use the hide command as well.

```javascript
"hide flower", // If flower is declared
"hide flower.png" // If flower isn't declared
```

You can use the same animations and positions when showing characters or images.
