---
description: Control the flow of your game
---

# Conditionals

Chances are, at some point you'll want to control the flow of your game depending on certain conditions, like jumping to certain labels or even show different dialogs depending on some condition.

To do this, Monogatari has Conditional objects, let's take a look at this example:

```
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

```
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

```
{'Conditional': {
    'Condition': function(){
        return this.storage ('money');
    },
    '0': 'jump goHomeEmptyHanded',
    '1': 'jump buyADollarItem',
    '2': 'jump buySomethingGood',
    '3': 'jump buyAComboMeal'
}},
```

You could write multiple conditional statements, that first check if you have 0 or not, then check if you have 1 or not, etc, but _this_ way you only need to write one. It's a little like a switch statement! Just keep in mind that this only works with strings, or things Javascript's weak typing can interpret as a string, and there's no 'else' so structure your `'Condition'` function accordingly.

