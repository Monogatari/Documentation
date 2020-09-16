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

Notice that `Start` string. By default, `Start` is the first label that monogatari will play when a game starts. As you can see, this label is pointing to a list of statements that monogatari will run one by one.

As we said before, labels are just like the chapters of a book but can also provide you with logical ways of dividing your game. As books can have many chapters, you can have many labels as well!

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

See that `'jump mylabel'`? that's how you can change between labels, the jump statement will take you to the label you give it.

