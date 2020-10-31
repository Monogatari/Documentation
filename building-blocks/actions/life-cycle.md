# Life Cycle



An action describes the functionality for a Monogatari statement, when Monogatari reads a part of the script \(a statement\), it will look for an action that matches the statement and run it.

The life cycle of an action is divided in three parts: Mounting, Application and Reverting.

## Mounting Cycle

The mounting cycle has 3 steps:

### Setup

Here the action needs to set up everything it will need for working generally, in this section an action will register the variables it needs such as object histories and state variables or even add the HTML contents to the document.

### Bind

Once the action has been setup, its time to bind all the necessary event listeners or perform more operations on the DOM once all elements have been setup.

### Init

Finally, once the action was setup and it performed all the needed bindings, it may declare or modify variables that needed the HTML to be setup first or perform any other needed final operations.

As noted, the Mounting cycle is mostly about getting everything setup for a correct operation of the action. The Application and Reverting cycles are used for the actual workings of an action in a game.

Before executing an action Monogatari will check if the current statement matches with the action, therefore the Action must implement a matching function. If the statement to match should be a String, the action must implement the `matchString ()` method, if it should be an Object, the action must implement the `matchObject ()` method. Both should return a `boolean` on whether the action matches the given statement or not.

## Application Cycle

The Application cycle refers to the cycle of an Action when it is run because of a statement in the script.

The Application Cycle has 3 steps as well:

### Will Apply

Executed when the action will be applied, if any operations need to be done before its application, this is the place.

### Apply

The application itself, this is where all the logic regarding the action must be applied. Of course every action will implement its own logic depending on what it has to do.

### Did Apply

Executed after the action was applied, this function is great for cleanup operations or any other thing that needs to be done after the action was applied.

## Revert Cycle

While the Application cycle is all about executing the action, the Revert cycle is the opposite and it reverts the things the Application cycle does. Reverting is used when the player goes back in the game and has equivalent steps to the Application Cycle:

### Will Revert

Executed when the action will be reverted, if any operations need to be done before its reversion such as checking for history elements or any other check, this is the place.

### Revert

The reversion of the action, its common that the actions revert to previous states or revert other changes done by the application of an action. Every action will implement its own logic depending on what it has to do.

### Did Revert

Executed after the action was reverted, this function is great for cleanup operations or any other thing that needs to be done after the action was reverted.

