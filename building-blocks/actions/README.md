# Actions

## Overview

Actions are what defines what any given statement in a script should do. 





 The following code displays a very simple example of an action that just does something when applied \(advancing through the game\) and something else when reverted \(rolling back through the game\). It will match all statements that start with `myaction`, for example:

```javascript
'myaction'
'myaction something'
'myaction one two three'
```

```javascript
class MyAction extends Monogatari.Action {

    static matchString ([action]) {
        return action === 'myaction';
    }

    constructor ([myaction, ...args]) {
        super ();
    }
    
    apply () {
        // Do something
    }
    
    revert () {
        // Do something
    }
}

MyAction.id = 'MyAction';
```

Now that we have our action class, we need to register it in Monogatari so it knows it exists:

```javascript
monogatari.registerAction (MyAction);
```

