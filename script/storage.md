## Storage

The storage is an object in which we can put everything we want to save when a player saves the game.

We have to create a property where the player can store his data in it. So in `storage.js` we start with...

```javascript
var storage = {
  player: {   // add property
    name: ""  // add placeholder
  }
}

// Syntax
var storage = {         // object
  property1: {         // property of object
    placeholder1: 0,   // integer of property
    placeholder2: ""   // string of property
  }
}
```

If we now want to get the name after saving one in there, this would look like this in the `script.js`.

```javascript
storage.player.name = "Monogatari";           // example for saving a name
"{{player.name}} is a visual novel engine."   // example for display the name
```

To offer more possibilities in the game and to have a simpler overview in the storage file, 
you can create as many properties as you want, just make sure to use a comma before adding a property. 
Here is an example...

```javascript
var storage = {
  player_info: {
    name: "",
    age: "",
    city: ""
  },
  
  player_stats: {
    hp: 100,
    mp: 100,
    inventory: {
      gold: 1000,
      iron: 10
    }
  }
}
```

Which can be accessed as follows (examples)...

```javascript
{"Input": {                                                             // call input statement
  "Text": "What is your name?",                                         // show text of the input box
  "Validation": function(input) { return input.trim().length > 0; },    // validation rule for the value
  "Save": function(input) {                                             // call save statement and start a function
      storage.player_info.name = input;                                 // store the value in the variable name
      storage.player_info.age = 18;                                     // store 18 in the variable age
  },
}},

function (){
  storage.player_info.name = "Georg";                                   // save "Georg" in variable name (overwrite old value)
  storage.player_stats.hp -= 50;                                        // decrease hp minus 50
  storage.player_stats.inventory.gold += 250;                           // add 250 gold
},

"{{player_info.name}} is {{player_info.age}} years old.",               // call name = "Georg" and age = 18
"{{player_stats.mp}} costs the ability 'Fire Storm'.",                  // call mp = "100"
"{{player_stats.inventory.gold}}g is in his bag of gold."               // call gold = 1250
```

If you want to see an example of the stat system (created with storage.js), [click me](https://hyuchia.com/Monogatari-Stat-System/).
