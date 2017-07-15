## Storage

There is a persistent storage object that you must use in case you want to keep some data from the user or other things.
This data will be loaded again when the user loads a saved game.

```javascript
var storage = {

}
```

Since the storage is a JSON object, you can save data just by setting a property:

```javascript
storage.Name = "User name";
```

Or by using a javascript statement:

```javascript
"$ storage.Name = "User name";"
```
