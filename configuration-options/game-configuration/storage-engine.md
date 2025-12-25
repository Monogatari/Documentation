# Storage

## Overview

Monogatari can use different storage engines so you can choose whichever works for your game best. This configuration can be found inside your `options.js` file. By default, it will look something like this:

```javascript
    // Define what storage engine should be used to save the game data. *
    // Adapters Available:
    // - LocalStorage: This one is used by default
    // - SessionStorage: Same as LocalStorage but will be cleared when the page
    //                      is closed.
    // - IndexedDB: The information is saved using the IndexedDB web API
    // - RemoteStorage: The information will be sent and retrieved from a given
    //                    URL Endpoint providing a REST API.
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

For remote storage, your configuration in `options.js` can be set as follow.

```javascript
    'Storage': {
        'Adapter': 'RemoteStorage',
        'Store': '',
        'Endpoint': 'https://foobar.com/gameSave'
    }
```

Or you may add a store name:

```javascript
    'Storage': {
        'Adapter': 'RemoteStorage',
        'Store': 'MyGame',
        'Endpoint': 'https://foobar.com/gameSave/'
    }
```

The storage engine concats the `Store` and `Endpoint` values as the actual RESTful API **endpoint url** to use:

```
https://foobar.com/gameSave/MyGame
```

### Implementing the Remote Storage

The storage mimic that of a localStorage, which is simple JSON object storage.

The **endpoint url** should implement the below API interface:

---

```http
GET [endpoint url]/
```

{% hint style="info" %}
Normally, retrieves all the values in the space in a key-value JSON object. If previous storage does not exist, return an empty JSON object: `{}`.

In keys-listing mode, return all keys stored in the space as a JSON array.
{% endhint %}

**Parameters**

| Name | Description |
| ---- | ----------- |
| keys | Boolean. If set to `true`, will switch to keys-listing mode. |

---

```http
DELETE [endpoint url]/
```

{% hint style="info" %}
Clear the entire storage object.

Equivlant to
```javascript
localStorage.clear();
```
{% endhint %}

---

```http
GET [endpoint url]/{key}
```

{% hint style="info" %}
Return the value of the key in the storage object.

Equivlant to
```javascript
localStorage.getItem(key);
```
{% endhint %}

---

```http
POST [endpoint url]/{key}
```

{% hint style="info" %}
Store the value in the storage object under the key.

The request body will be the JSON value to store.

Equivlant to
```javascript
localStorage.setItem(key, value);
```
{% endhint %}

---

```http
PUT [endpoint url]/{key}
```

{% hint style="info" %}
Update the value in the storage object under the key.

The request body will be the JSON value to store. The original content
should be overwritten.

Equivlant to
```javascript
localStorage.setItem(key, value);
```
{% endhint %}

---

```http
DELETE [endpoint url]/{key}
```

{% hint style="info" %}
Return the value of the key in the storage object.

Equivlant to
```javascript
localStorage.removeItem(key);
````
{% endhint %}
