# Scenes

The scenes clear the screen and change the background. They will also clear the screen, removing the text, characters and images displayed.

You can either use images or css for the scenes. They will change with a fadeIn effect by default, currently that's the only animation available but more will be added.

If you'll use images, must declare them first, every scene image file must be placed in the scenes directory inside the img directory.

```javascript
var scene = {
    "mountain": "mountain.svg",
    "sea": "sea.png"
}
```

Now, to change the scene, just use the scene command. Syntax: "scene \[Scene Identifier\]"

```javascript
"scene mountain"
```

If you'll use css to set your own background style, you must use the scene command as well. Syntax: "scene \[CSS\]": These are valid ways to use it:

```javascript
"scene #fff"
"scene rgb(0,0,0)"
"scene url('img/scenes/mountain.svg')"
```

