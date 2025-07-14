---
description: Install all the tools you need to create your visual novel
---

# Step 1: Setup Your Environment

To develop in Monogatari you'll need the same tools used for web development. This means that all you need is a **text editor**, with which **\*\*you'll be editing&#x20;**_**HTML, JavaScript**_**&#x20;and&#x20;**_**CSS**_**&#x20;files.** Optionall&#x79;**, you may also use a** local web server\*\* while developing your novel.

## Getting a Browser

You already have one of this but is it the best one for you to develop your game?&#x20;

We recommend you using either [**Chrome**](https://www.google.com/chrome/) **or** [**Firefox** ](https://www.mozilla.org/en-US/firefox/)**for development**. While your game will run in any modern browser, not all of them offer a great experience while developing. Both Chrome and Firefox have some pretty cool developer tools that will certainly make your life easier.

## Getting a Code Editor

What editor to use comes down to personal preference but almost any text / code editor should work! You can even use _Windows Notepad._ However, to make your life easier, you should really try using a text editor that has been created for coding since those have features such as code syntax highlighting (all the different colors for functions, variables etc.) and some may even help you out while writing your code!

Here are some that are pretty awesome to get you started and they are completely **free** to use:

1. [Visual Studio Code](https://code.visualstudio.com/)
2. [Atom](https://atom.io/)
3. [Brackets](http://brackets.io/)

If you've never used a code editor before, feel free to try them all! You should stick to the one you feel more comfortable with.

## Getting a Local Web Server (Optional)

A web server, in simple terms is the piece of software that retrieves and sends the correct files to your browser when you enter a website. While it is completely optional to install one, it's important to establish why you would want a local web server.

Here is a list of features that will only work if your game is running under a web server:

* [Asset preloading](../configuration-options/game-configuration/asset-preloading.md): Asset preloading, as it's name sounds, is the feature that allows your game to preload all images, sounds, videos etc. and save them up in the browser cache so that they are loaded faster and work offline. This feature requires a web server since it uses service workers and those are only available through HTTP or HTTPS protocols.

### Which server should you use?

There are many web servers out there, some that may come up on search results include Apache and Nginx, however, these may be more complicated and a bit too much for what you'll need.

The most simple option is to install the [Web Server for Chrome](https://chrome.google.com/webstore/detail/web-server-for-chrome/ofhbbkphhbklhfoeikjpcbhemlocgigb) extension that will allow you to create a very simple web server using the Chrome browser. Even if you prefer not to use chrome for your development, you can simply set up the server and then access it through any other browser.
