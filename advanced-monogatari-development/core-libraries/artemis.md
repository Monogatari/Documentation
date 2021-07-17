---
description: 'DOM manipulation, storage, HTTP requests handling, text transformations, etc.'
---

# Artemis

Artemis is a JavaScript Library that aims to provide common utilities needed during development such as DOM manipulation, a wrapper for client based Storage and other functions that may be useful for web app development.

## Using it
Artemis is provided as an UMD, therefore it's possible to use it either on a browser as a global library, using es6 modules or nodejs modules.

### Browser

```html
<script src='./artemis.min.js'></script>
```

```javascript
const { $_, Text } = Artemis;
```

### ES6 Modules

```javascript
import { $_, Text } from '@aegis-framework/artemis';
```

### Node JS

```javascript
const { $_, Text } = require ('@aegis-framework/artemis');
```


Below are some simple examples but you can read the full [documentation of each class](https://gitlab.com/AegisFramework/Artemis/tree/master/docs) for more details.

## Classes

### DOM
Artemis core library focuses on DOM manipulation, providing a jQuery-like experience and API

```javascript
$_ready (()=> {
	$_('body').append ('<h1>Some Title</h1>');
    $_('h1').text ('A different title');
    $_('h1').style ('color', '#424242');
});
```

### Form
Artemis also includes a small form utility class that helps with filling and retrieving values from a form.

```html
<form data-form="MyForm">
	<input type="text" name="SomeInput">
	<input type="text" name="OtherInput">
</form>
```

```javascript
Form.fill ('MyForm', {
	'SomeInput': 'Here is some Value',
    'OtherInput': 'And here’s another one'
});

console.log (Form.values ('MyForm'));
```

### Space

The Space Library is a wrapper for simple storage solutions as Local and Session storage but provides data independence through storage namespaces and versioning.

```javascript
let space = new Space (SpaceAdapter.LocalStorage, {
	name: 'Storage',
	version: '0.1.0'
});

space.set ('Test', {
    value: 'Some Value'
}).then (({key, value}) => {
    console.log ('The value was inserted correctly!');
});

space.get ('Test').then ((value) => {
    return value;
}).then (({key, value}) => {
    console.log (value);
});

space = new Space (SpaceAdapter.LocalStorage, {
	name: 'Storage',
	version: '0.1.1'
});

space.upgrade ('0.1.0', '0.1.1', (storage) => {
    return storage.set ('Test', {
		value: 'Other Value'
	});
});
```

### Request
The request library provides a simple way to send HTTP requests using the fetch API.

```javascript
Request.get ('https://example.com/api/', {
	'someQueryParam': 'Some Query Value!'
}).then ((response) => {
	return response.text ();
}).then ((text) => {
	console.log (text);
});

Request.post ('https://example.com/api/', {
	'someKey': 'Some Value!'
}).then ((response) => {
	return response.text ();
}).then ((text) => {
	console.log (text);
});
```

### Platform
The platform library provides several utility methods to obtain information about the platform in which the code is running.

```javascript
if (Platform.mobile ('Android')) {
	console.log ('You are running this on Android!');
} else if (Platform.mobile ()) {
	console.log ('You are running this on some kind of mobile device!');
} else if (Platform.desktop ('macOS')) {
	console.log ('You are running this on a Mac!');
}

if (Platform.electron ()) {
	console.log ('You are running this on a Electron!');
} else if (Platform.cordova ()) {
	console.log ('You are running this on a Cordova!');
}
```

### Text
The text library provides simple utility methods to perform text transformations or other text related functions.

```javascript
console.log (Text.capitalize ('is this text capitalized?'));
// Logs: Is This Text Capitalized?

console.log (Text.suffix ('Hello', 'Hello how are you?'));
// Logs: how are you?

console.log (Text.prefix ('how are you?', 'Hello how are you?'));
// Logs: Hello 
```

### Util
The util library provides diverse methods that could be useful for some applications

```javascript
console.log (Util.uuid ());
// Logs: Some UUID such as 116a7d96-8c6c-46ee-a9e1-3c7183e691b5

function test () {
	console.log ('A simple Function');
}

Util.callAsync (test).then (() => {
	console.log ('Test was executed and a promise was inserted so test behaves like a function using promises');
});

```
{"mode":"full","isActive":false}

