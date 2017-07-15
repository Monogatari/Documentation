## Getting Started

<div class="warning md-depth-2"> This documentation is still under revision.</div>

The first thing about Monogatari that you should probably know is that with it, your visual novel is a web page first and a game later. That means that Monogatari has been created specifically for the web, putting things like responsiveness first. You don't necessarily need to think of your game this way as well, but you'll certainly take the most out of Monogatari if you do.

So, to develop in Monogatari you would need the same as to develop a webpage, you just need a text editor capable of editing HTML, Javascript and CSS, which means that pretty much any text editor should work, even Windows NotePad.

Some recommended (and free) ones include:

* [Atom](https://atom.io/)
* [Brackets](http://brackets.io/)
* [Visual Studio Code](https://code.visualstudio.com)

### Getting Help

While this documentation covers many parts of Monogatari's functioning, it does not cover everything you could actually do with it, but remember, your VN is a website now, so if you google something, for example if you want something to happen when someone clicks an image, you can google it as "javascript click image", there's no need to look for a Monogatari-specific answer, everything that applies to a website also applies for Monogatari.

If you have any doubt, problem or just want some help please contact me, I'll be glad to help. You can contact me by <a class="mailto" href="diego(at)hyuchia(dot)com" > Mail</a>, [Twitter](https://twitter.com/Hyuchia), [Google+](https://plus.google.com/+HyuchiaDiego/) and [Mastodon](https://mastodon.social/@HyuchiaDiego) 

If you like Monogatari and would like to support it's creation you can do so by supporting me via [Patreon](https://www.patreon.com/Hyuchia), you can even get the personalized support reward for Monogatari (which is something I do for free if you contact me but choosing it in Patreon shows your support :) )

### Understanding the Parts
You'll see many directories and files when you download Monogatari and you need to understand what every file is for.

#### Directories

| Directory | Contains |
| ------------- | ------------- |
| audio | Audio files (Music, voice and sounds). |
| error | Custom error pages, you may modify those as you wish. |
| fonts | Font Awesome by default,every other font should be placed here as well |
| style | CSS files for your project. |
| img | All the images for your project (UI, Backgrounds, characters etc.) |
| js | All the things that'll make your VN work |


#### JS Directory

| File | Contains |
| ------------- | ------------- |
| main.js | If you want to add more javascript, this is the file to do it! |
| options.js | Initial settings of your game and engine settings. |
| script.js | The main script of your game. (Here's where your story, characters, images etc are declared) |
| strings.js | UI translations used for internationalization. |
| monogatari.js | The engine itself, you may modify it but only if you know what you're doing. |
| plugins.js | File for adding plugins.|
| artemis.min.js | Aegis JavaScript library for DOM manipulation used in the engine. |
| jquery.min.js | jQuery library for user defined functionality. |
| particles.min.js | Javascript Particles library. |


#### Style Directory

| File | Contains |
| ------------- | ------------- |
| main.css | Add your styling in this file. |
| monogatari.css | File with the initial styling of Monogatari. |
| csshake.min.css | CSS Shake Animations Library. |
| animate.min.css | CSS Animations Library. |
| font-awesome.min.css | CSS of Font Awesome. |
| normalize.min.css | CSS Normalizer |
