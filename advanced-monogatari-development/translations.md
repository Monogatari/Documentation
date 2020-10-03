---
description: Learn everything about translating Monogatari's UI to other languages!
---

# Translations

## Overview

Apart from allowing you to have a script for different languages, Monogatari's UI can also be translated to multiple languages. If you are someone who knows a language different from English, your help on translating the project is more than welcome!

## Getting started

The first step is to figure out whether a translation for you language already exists or if it has to be created, you can find all languages available [here](https://github.com/Monogatari/Monogatari/tree/develop/src/translations).

If there is a translation already available for your language, then all you'll have to do is update or add whatever strings are missing, if there isn't one yet, then you'll have to create a new file for it.

All translations take the [English strings file](https://github.com/Monogatari/Monogatari/blob/develop/src/translations/English.js) as its base so you'll need to check it out to see what you need to translate. Below is a sample of the file, be aware this is for demonstration purposes only and may be outdated so you should always check [the source file instead](https://github.com/Monogatari/Monogatari/blob/develop/src/translations/English.js). It is important that you only translate the strings on the right, as opposed to their keys on the left \(`'SomeKey': 'Some string to translate'`\).

{% code title="English.js" %}
```javascript
/**
 * ============================================================
 * English
 * ============================================================
 *
 * Translators:
 *
 * Hyuchia <diego@hyuchia.com>
 */



export default {
	'AdvanceHelp': 'To advance through the game, left-click or tap anywhere on the game screen or press the space key',
	'AllowPlayback': 'Click here to allow audio playback',
	'Audio': 'Audio',
	'AutoPlay': 'Auto',
	'AutoPlayButton': 'Enable auto play',
	'AutoPlaySpeed': 'Autoplay Speed',

	'Back': 'Back',
	'BackButton': 'Go back',

	'Cancel': 'Cancel',
	'Close': 'Close',
	'Confirm': 'Do you want to quit?',
	'Credits': 'Credits',

	'Delete': 'Delete',
	'DialogLogButton': 'Show the dialog log',

	'FullScreen': 'Full Screen',

	'Gallery': 'Gallery',

	'Help': 'Help',
	'Hide': 'Hide',
	'HideButton': 'Hide the text box',

	'iOSAudioWarning': 'Audio settings are not supported on iOS',

	'KeyboardShortcuts': 'Keyboard Shortcuts',

	'Language': 'Language',
	'Load': 'Load',
	'LoadAutoSaveSlots': 'Auto Saved Games',
	'LoadButton': 'Open the Load Screen',
	'Loading': 'Loading',
	'LoadingMessage': 'Wait while the assets are loaded',
	'LoadSlots': 'Saved Games',
	'LocalStorageWarning': 'Local Storage is not available in this browser',
	'Log': 'Log',

	'Music': 'Music Volume',

	'NewContent': 'There is new content available, reload the page to get the latest version',
	'NoSavedGames': 'No saved games',
	'NoAutoSavedGames': 'No automatically saved games',
	'NoDialogsAvailable': 'No dialogs available. Dialogs will appear here as they show up',

	'OK': 'OK',
	'OrientationWarning': 'Please rotate your device to play',
	'Overwrite': 'Overwrite',

	'QuickButtons': 'Quick Menu Buttons',
	'QuickMenu': 'Quick Menu',
	'Quit': 'Quit',
	'QuitButton': 'Quit Game',

	'Resolution': 'Resolution',

	'Save': 'Save',
	'SaveButton': 'Open the Save Screen',
	'SaveInSlot': 'Save in slot',
	'SelectYourLanguage': 'Select your language',
	'Settings': 'Settings',
	'SettingsButton': 'Open the Settings Screen',
	'Show': 'Show',
	'Skip': 'Skip',
	'SkipButton': 'Enter skip mode',
	'SlotDeletion': 'Are you sure you want to delete this slot?',
	'SlotOverwrite': 'Are you sure you want to overwrite this slot?',
	'Sound': 'Sound Volume',
	'Start': 'Start',
	'Stop': 'Stop',

	'TextSpeed': 'Text Speed',

	'Video': 'Video Volume',
	'Voice': 'Voice Volume',

	'Windowed': 'Windowed'
};
```
{% endcode %}

## Updating an Available Language

If a translation for your language already existed, then all you need to do is check the English file and compare it to the one in your language to make sure every string translated is updated \(meaning the English version and the translation match on its wording/meaning\) and adding any string that was not previously there.

## Adding a New Language

If there was no translation for your language available, then you first need to create a file for it. The file should be placed next to all the other translations and should be named after the language you are translating for. Preferably, keeping the name of your language in the language itself so:

> English =&gt; `English.js`
>
> Spanish =&gt; `Español.js`
>
> Japanese =&gt; `日本語.js`

You get the idea. Once you've created the file, simply copy the contents of the English translation file and you're all set to start translating all the strings there!

## Credit Yourself

When you finish, be sure to place your name/nickname on the translations file, you can also leave your email or website next to it. You did an awesome work so you deserve to take credit for it!

