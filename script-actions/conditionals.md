---
description: Control the flow of your game
---

# Conditionals

Chances are, at some point you'll want to control the flow of your game depending on certain conditions, like jumping to certain labels or even show different dialogs depending on some condition.

To do this, Monogatari has Conditional objects, let's take a look at this example:

```javascript
{'Conditional': {
    'Condition': function () {
        return this.storage ('evelyn_name') == 'Evelyn';
    },
    'True': 'e Evelyn... That’s a lovely name! I love it!',
    'False': 'e {{evelyn_name}}... Yeah, sounds good!'
}},
```

As you can see, a Conditional is made up of 3 properties, a `'Condition'`, the function that will be used to determine whether the condition is met or not. In these case, we are checking if the variable `storage.evelyn_name` is equal to `'Evelyn'`, if the condition returns `true`, the statement inside the `'True'` property will be run, if it's false then the statement inside the `'False'` property will be run.

In this case, those statements are dialogs so that simply means that if the condition is true, the first dialog will be shown, if not then the second one will be shown.

Of course dialogs is not the only thing we can do here, we can also use Conditionals to jump to certain labels like this:

```javascript
{'Conditional': {
    'Condition': function(){
        return this.storage ('played');
    },
    'True': 'jump Played',
    'False': 'jump NewGame'
}},
```

## Non-Boolean Conditions

The `'Conditional'` object also supports strings. In this example, assume your storage contains a variable called `'money'` and that the money variable represents currency the player can find, and then an ending is chosen when they come to a place to purchase food.

```javascript
{'Conditional': {
    'Condition': function(){
        if(this.storage().money < 1) {
            return "Too poor";
        } else if (this.storage < 4) {
            return this.storage ('money') + '';
        } else {
            return 'Rich';
        }
    },
    'Too poor': 'jump goHomeEmptyHanded',
    '1': 'jump buyADollarItem',
    '2': 'jump buySomethingGood',
    '3': 'jump buyAComboMeal'
    'Rich': 'jump buyTheWholeStore',
}},
```

You could write multiple conditional statements, that first check if you have 0 or not, then check if you have 1 or not, etc, but _this_ way you only need to write one single conditional branch that functions a little like a switch statement!

Please note: This only works with strings. You can't use Numbers in place of keys, which is why in the above example we add an empty string to our numerical value `money` so that instead of returning a number, it would return the number as a string.

Also note: The Conditional object does not have an `else` of any kind, and Monogatari will throw an error if the Condition block returns something that is not found in the list of choices. For this reason, in the above example, we accounted for cases where money is less than 1, or where money is 4 or more. This way, if the person playing the game managed to acquire 5, 6, or even _Seven_ whole dollars, the game will know what to do with that kind of money.

