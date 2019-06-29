---
description: Translate Monogatari to other languages!
---

# Translations

## Overview

Apart from translating the game contents, Monogatari's UI can also be translated to multiple languages. If you are someone who knows a language different from English, your help on translating the project is more than welcome!

## Getting started

The file containing all the translations is found at `js/strings.js`. In it, you'll find multiple JSON objects describing the translations for each string on its own language. 

{% code-tabs %}
{% code-tabs-item title="strings.js" %}
```javascript
"English": {
		"AdvanceHelp": "To advance through the game, press the space key or click.",
		"Audio": "Audio",
		"AutoPlay": "Auto",
		"AutoPlaySpeed": "Autoplay Speed",

		"Back": "Back",
		"BackButton": "Back.",

		"Cancel": "Cancel",
		"Close": "Close",
		"Confirm": "Do you want to quit?",

		"FullScreen": "Full Screen",

		"Help": "Help",
		"Hide": "Hide",
		"HideButton": "Hide Text.",

		"iOSAudioWarning": "Audio settings are not supported on iOS.",

		"Language": "Language",
		"Load": "Load",
		"LoadAutoSaveSlots": "Auto Saved Games",
		"LoadButton": "Open the Load Screen.",
		"Loading": "Loading",
		"LoadingMessage": "Wait while the assets are loaded.",
		"LoadSlots": "Saved Games",
		"LocalStorageWarning": "Local Storage is not available in this browser.",

		"Music": "Music Volume",

		"NoSavedGames": "No saved games.",
		"NoAutoSavedGames": "No automatically saved games.",

		"Overwrite": "Overwrite",

		"QuickButtons": "Quick Menu Buttons",
		"Quit": "Quit",
		"QuitButton": "Quit Game.",

		"Resolution": "Resolution",

		"Save": "Save",
		"SaveButon": "Open the Save Screen.",
		"SaveInSlot": "Save in slot",
		"Settings": "Settings",
		"SettingsButton": "Open the Settings Screen.",
		"Show": "Show",
		"SlotDeletion": "Are you sure you want to delete this slot?",
		"SlotOverwrite": "Are you sure you want to overwrite this slot?",
		"Sound": "Sound Volume",
		"Start": "Start",
		"Stop": "Stop",

		"TextSpeed": "Text Speed",

		"Voice": "Voice Volume",

		"Windowed": "Windowed"
},
```
{% endcode-tabs-item %}
{% endcode-tabs %}

To add a new language, simply copy one of these blocks and add your own translations!

