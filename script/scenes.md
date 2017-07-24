## Scenes
The scenes clear the screen and change the background. They will also remove the text, characters and images displayed.

You can either use images or CSS properties like colors as backgrounds. 

If you'll use images, must declare them first, every scene image file must be placed in the scenes directory inside the img directory. Remember to add these files to your `service-worker.js` file if you want to improve asset preloading as stated in the [Asset Preload Section](https://monogatari.io/documentation/configuration/asset-preload/)

```javascript
var scenes = {
    "mountain": "mountain.svg",
    "sea": "sea.png"
}
```

Now, to change the scene, just use the scene command. Syntax: "scene [Scene Identifier]"

```javascript
"scene mountain"
```

If you'll use css to set your own background style, you must use the scene command as well. Syntax: "scene [CSS]":
These are valid ways to use it:

```javascript
"scene #fff"
"scene rgb(0,0,0)"
"scene url('img/scenes/mountain.svg')"
```

### Animations

Since Monogatari v1.3.2, it is possible to use the same animations for characters and scenes, to use an animation to display your scene, you must use the scene command as follows:

 Syntax: "scene [CSS or Image Identifier] with [Animation Name]"

```javascript
"scene mountain with fadeIn"
```

Remember you can see the list of animations and visualize them [here](https://daneden.github.io/animate.css/).

You can also use CSS to create your own animations, you'll have to apply them to a CSS class and then use the scene statement as follows:

Syntax: "scene [CSS or Image Identifier] with [CSS Class Name]"

For example, note the following CSS code creating a simple Ken Burn Animation:

```css
.ken-burn {
    animation-name: ken-burns; /* Name of the animation to use */
    animation-duration: 30s;
    animation-iteration-count: infinite; /* 1 if it should only move once */
    animation-timing-function: ease;
    animation-fill-mode: forwards;
    animation-delay: 0s;
    -moz-transition: ease 1s all;
    -o-transition: ease 1s all;
    -webkit-transition: ease 1s all;
    transition: ease 1s all;
}


@keyframes ken-burns {
    0%    { 
        -webkit-transform: translateX(0); 
    }
    50%    {
        -webkit-transform: translateX(-500px);
    }
    100%  {
        -webkit-transform: translateX(0px); 
    }
}
```

In order to use that animation within your game, it would be as simple as this:

```javascript
"scene mountain with ken-burn"
```