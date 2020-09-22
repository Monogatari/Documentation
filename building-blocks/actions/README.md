# Actions

Actions are what defines what any given statement in a script should do.

 The following code displays the most simple action you can create where it just does something when applied \(advancing through the game\) and something else when reverted \(rolling back through the game\).

```javascript
class MyAction extends Monogatari.Action {

    static matchString ([action]) {
        return action === 'myaction';
    }

    constructor (...args) {
        super (...args);
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

