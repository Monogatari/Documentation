## Saving

### Multiple Games in the same domain.

You may have multiple games in the same domain, if you keep the default save name in all of them, you'll notice they'll share the save and load slots. Thats why, you can change the name prefix of the save slots in the options.js file, just change the value of the engine["slots"] variable.

### Change Number of Save Slots

You can easily increase or decrease the number of save slots available for your game. Simply go to the options.js file and change the engine["Slots"] value to any number you want.

### AutoSaving

You can make your game have autosaves every certain time, to do so, just change in the options.js file the "AutoSave" property.

By default, this property is set to 0, meaning AutoSaving is off.

```javascript
"AutoSave": 0
```

You can change this number to the number of every minutes you want your game to be autosaved. For example, the following will autosave the game every 5 minutes:

```javascript
"AutoSave": 5
```

You can also change the AutoSave Labels Name, to do so change the "AutoSaveLabel" property in the options.js file.
