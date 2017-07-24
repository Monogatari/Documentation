## Asset Preload
When releasing your game online, the asset loading is one of the most important issues to be solved, it must be nice enough so that people can enjoy playing your game online even on slow connections and that's why since v1.3.2 Asset Preloading is built in right in the engine.

### Built In Preloading
The asset preloading will show a progress bar when you enter the game, the entire preloading can be disabled using the `Preload` property in the options.js:

This property default value is true meaning it will show the Preload Screen and do all the Asset Preloading

```javascript
"Preload": true
```

To skip it, just change the value to false but remember that every asset will be loaded when you use it and may make a poor experience for users on slow connections.

```javascript
"Preload": false
```

### Service Workers Cache
One of the benefits the Service Workers in Monogatari provide is the use of the Cache to serve your files even when offline once they've been loaded, this means that instead of taking the asset from the network, Monogatari will first check if the asset has been loaded in the cache, if it has then it will inmediatly load it from there but still making a network request to update the asset in the cache. 

This means the users will see the asset load instantly and will still receive the updates you make. More details about this strategy are [available here](https://serviceworke.rs/strategy-cache-and-update_service-worker_doc.html) and [here](https://css-tricks.com/serviceworker-for-offline/).

This functionality is inside the `service-worker.js` file. There you'll need to take notice of the three properties: `name`, `version` and `files`.

The `name` and `version` properties are used to control the cache of your game, change the `name` to your game's name, whith no spaces or special characters and the `version` property as a control.

```javascript
// The name of your game, no spaces or special characters.
var name = 'Monogatari';

// The version of the cache, changing this will force everything to be cached
// again.
var version = '0.1.0';
```

What does using the `version` as a control means? Well, lets take a look at the `files` variable first, this array defines all the files you want to store in the cache, by default this just caches files that most likely won't change nad it's up to you to add your game assets and other files:

```javascript
var files = [

	// General Files
	'/',
	'manifest.json',

	// HTML Files
	// 'index.html',

	// CSS Files
	'style/animate.min.css',
	'style/csshake.min.css',
	'style/font-awesome.min.css',
	'style/normalize.min.css',
	// 'style/monogatari.css',
	// 'style/main.css',

	// JavaScript Files
	'js/particles.min.js',
	'js/jquery.min.js',
	'js/artemis.min.js',
	'js/plugins.js',
	// js/monogatari.js',
	// js/strings.js',
	// js/options.js',
	// js/script.js',

	// Fonts
	'fonts/FontAwesome.otf',
	'fonts/fontawesome-webfont.eot',
	'fonts/fontawesome-webfont.svg',
	'fonts/fontawesome-webfont.ttf',
	'fonts/fontawesome-webfont.woff',
	'fonts/fontawesome-webfont.woff2',

	// App Images
	'img/favicon.ico',

	// Scene Images
	//'img/scenes/',

	// Character Images
	//'img/characters/',

	// Side Images
	//'img/characters/',

	// UI Images
	//'img/ui/',

	// Music Audio
	// 'audio/music/',

	// Voice Audio
	// 'audio/voice/'

	// Sound Audio
	// 'audio/sound/'
];
```

If you were to leave it like that, offline playing would not be possible because you are not caching your assets such as images and audio, more importantly you can notice how important files like the monogatari.js files are commented out in that code, this is mainly to ease your development and prevent you having cache problems but for deployment, you should uncomment those out and add your own assets files as well. Let's take a look at how this variable looks like for the [demo in the website](https://monogatari.io/demo/):

```javascript
var files = [
	'/',
	'manifest.json',
	// HTML Files
	'index.html',

	// CSS Files
	'style/animate.min.css',
	'style/csshake.min.css',
	'style/font-awesome.min.css',
	'style/normalize.min.css',
	'style/monogatari.css',
	'style/main.css',

	// JavaScript Files
	'js/particles.min.js',
	'js/jquery.min.js',
	'js/artemis.min.js',
	'js/plugins.js',
	'js/monogatari.js',
	'js/options.js',
	'js/strings.js',
	'js/script.js',

	// Fonts
	'fonts/FontAwesome.otf',
	'fonts/fontawesome-webfont.eot',
	'fonts/fontawesome-webfont.svg',
	'fonts/fontawesome-webfont.ttf',
	'fonts/fontawesome-webfont.woff',
	'fonts/fontawesome-webfont.woff2',

	// Scene Images
	'img/scenes/classroom.jpg',
	'img/scenes/home.png',
	'img/scenes/library.png',
	'img/scenes/room.jpg',
	'img/scenes/sea.jpg',

	// Character Images
	'img/characters/Evelyn/ahahahah.png',
	'img/characters/Evelyn/hehehehe.png',
	'img/characters/Evelyn/hmph!.png',
	'img/characters/Evelyn/ngggg....png',
	'img/characters/Evelyn/normal.png',
	'img/characters/Evelyn/tongue.png',
	'img/characters/Evelyn/uhh.png',
	'img/characters/Evelyn/wink.png',

	// UI Images
	'img/ui/main-screen.svg'
];
```

You can see how the core files were uncommented, the used images were added as well as the sound file. The video file used inside the demo could also be cached but it was decided not to just to save up space. 

By caching all the assets of the demo, you can play it even offline once you've loaded the assets once!

Back to the `version` variable, changing the version will force all the assets to re-cache, useful specially when you make significant changes to them but remember that the cache strategy used will update your files eventually without the need of changing this version. Also the version does not need to be changed when removing/adding files to the cache. Most of the times you won't need to change it at all.

This makes part of the effort to transform Monogatari games deployed online into full [Progressive Web Apps](https://en.wikipedia.org/wiki/Progressive_web_app) which provides a lot of benefits. You can read more about what you need to do and what that means for your players in the [Web Deployment Section](https://monogatari.io/documentation/release/web/)

Use of Service Workers can also be disabled from the `options.js` file using the "ServiceWorkers" property.

This property default value is true meaning it will make use of Service Workers to cache your assets, Service Workers may be used for other activities in the future as well, disabling this option will disable them all.

```javascript
"ServiceWorkers": true
```

To disable it, just change it to false but remember that every asset will be loaded when you use it and may make a poor experience for users on slow connections.

```javascript
"ServiceWorkers": false
```

It's important to note that Service Workers are only available through HTTP or HTTPS protocols, meaning they will only be available when serving your game through a server. If you just open the files on the browser, you'll see an URL that starts with `file://` and then in the console you'll find an error that says:

`Failed to register a ServiceWorker: The URL protocol of the current origin ('null') is not supported.`

Or, if using a newer Monogatari version, a warning that says:

`Service Workers are available only when serving your files through a server, once you upload your game this warning will go away. You can also try using a simple server like this one for development: https://chrome.google.com/webstore/detail/web-server-for-chrome/ofhbbkphhbklhfoeikjpcbhemlocgigb/`


Either way is completely normal, as soon as you upload your game online to make it playable, that message will go away on it's own.