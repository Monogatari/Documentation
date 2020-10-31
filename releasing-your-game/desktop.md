# Desktop App

Monogatari comes with support for Electron out of the box.

## Requirements

* [Node.js](https://nodejs.org/en/)
* [Yarn](https://yarnpkg.com/)

```text
$ yarn install
```

## Windows

```text
$ yarn build:windows
```

## macOS

{% hint style="warning" %}
Since macOS Catalina, Apple [requires all apps made for mac to be notarized](https://developer.apple.com/news/?id=12232019a). This requires you to both own a mac and register as an Apple Developer \(with an anual cost of $100 USD\). If you want to distribute your game for mac but don't meet with these requirements, we can notarize your app for you, just reach out !
{% endhint %}

```text
$ yarn build:mac
```

## Linux

```text
$ yarn build:linux
```

