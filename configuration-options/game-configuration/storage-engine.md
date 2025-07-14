# Storage

## Overview

Monogatari can use different storage engines so you can choose whichever works for your game best. This configuration can be found inside your `options.js` file. By default, it will look something like this:

```javascript
	// Define what storage engine should be used to save the game data. *
	// Adapters Available:
	// - LocalStorage: This one is used by default
	// - SessionStorage: Same as LocalStorage but will be cleared when the page
	// 					 is closed.
	// - IndexedDB: The information is saved using the IndexedDB web API
	// - RemoteStorage: The information will be sent and retrieved from a given
	//					URL Endpoint providing a REST API.
	'Storage': {
		'Adapter': 'LocalStorage',
		'Store': 'GameData',
		'Endpoint': ''
	}
```

{% hint style="warning" %}
When releasing a game as a website, it's important to note that if people enter your game using the incognito mode in their browsers, their data will be erased when they close that window unless you choose to roll out your own server-based storage with the [Remote Storage](storage-engine.md#remote-storage) option.
{% endhint %}

## Local Storage

This is the default storage engine used by Monogatari and it uses your browser's [local storage](https://developer.mozilla.org/en-US/docs/Web/API/Window/localStorage).

## Session Storage

The session storage works just like the local storage engine with the important difference that **their data will be erased** the moment they close the game.

## Indexed DB

## Remote Storage

