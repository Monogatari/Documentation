## Storage

The storage is an object in which we can put everything inside we want to save when a player saves the game.

We have to create a property where the player can store his data in it. So in `storage.js` we start with...

```javascript
var storage = {
  player: { // add property
    name: "" // add placeholder
  }
}

// Syntax
var storage = { // object
  property#1: { // property of object
    placeholder#1: 0, // integer of property
    placeholder#2: "" // string of property
  }
}
```

If we now want to get the name after saving one in there, this would look like this in the `script.js`.

```javascript
storage.player.name = "Monogatari"; // example for saving a name
"{{player.name}} is a visual novel engine." // example for display the name
```

To offer more possibilities in the game and to have a simpler overview in the storage file, 
you can create as many properties as you like with a comma separated. Here an example...

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

Which can be accessed as follows...

```javascript
// examples
storage.player_info.name = "Georg";
storage.player_stats.hp -= 50;
storage.player_stats.inventory.gold += 250;

"{{player_info.name}} is {{player_info.age}} years old.",
"{{player_stats.mp}} costs the ability 'Fire Storm'.",
"{{player_stats.inventory.gold}}g is in his bag of gold."
```

The further you go into the storage or property, the longer the save and call statement will be.<br>
If you want to see an example of the stat system (created with storage.js), [click me](https://hyuchia.com/Monogatari-Stat-System/).
