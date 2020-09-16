# Script & Labels

## Overview

The script is the soul and body of your game, it is the place where you define everything that happens on it. It is made out of labels that are just like the chapters of a book and inside of each label, you have a list of statements that will be run one by one as your story unfolds.

## Labels

Let's take a look at an incredibly simple script, this is the most basic script a game could have:

```javascript
monogatari.script ({
    'Start': [
        'This is a statement.',
        'end'
    ]
});
```

Notice that `Start` string. By default, `Start` is the first label that Monogatari will play when a game starts. As you can see, this label is pointing to a list of statements that monogatari will run one by one.

As we said before, labels are just like the chapters of a book but can also provide you with logical ways of dividing your game. 

### Jumping between labels

As books can have many chapters, you can have many labels as well! Not only that, you can make your game move from one label to another using the [Jump action](../script-actions/jump.md).

```javascript
monogatari.script ({
    'Start':[
        'This is a statement.',
        'jump mylabel'
    ],
    'mylabel':[
        'This is another statement.',
        'Pretty easy huh?',
        'end'
    ]
});
```

As you can see from this script, we have two labels, `Start` and `mylabel.` Players will start in the `Start` one by default which will print out the first dialog and when the player clicks to advance, it will reach the `jump mylabel` statement. When reached, the game will simply carry on  with the statements inside the `mylabel` label without the player ever noticing something happened.

## Translating your  Script

Making your game available in many languages is super simple, head over to the Internationalization guide to learn more.

{% page-ref page="../configuration-options/game-configuration/internationalization.md" %}

## Splitting your script in multiple files

As your game script grows, having it all in the same file might become troublesome. Splitting your script into multiple files is a good way to get organized and make it less cluttered. Learn how to do this in the Split files section.

{% page-ref page="../configuration-options/split.md" %}



