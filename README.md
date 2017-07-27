## Getting Started

<div class="warning md-depth-2"> This documentation is still under revision.</div>

The first thing about Monogatari that you should probably know is that with it, your visual novel is a web page first and a game later. That means that Monogatari has been created specifically for the web, putting things like responsiveness (the fact that your game will adapt to any screen or device size) first. You don't necessarily need to think of your game this way as well, but you'll certainly take the most out of Monogatari if you do.

### Set up your environment

To develop in Monogatari you would need the same as to develop a webpage, you just need a text editor capable of editing HTML, Javascript and CSS, which means that pretty much any text editor should work, even Windows NotePad but to make it easier, you probably want one with code syntax highlightning.

Some recommended (and free) ones include:

* [Atom](https://atom.io/)
* [Brackets](http://brackets.io/)
* [Visual Studio Code](https://code.visualstudio.com)

Take a look at them and pick the one you like the most and feel comfortable with, this will be your main tool from now on.

Now, you can always open a website by just clicking the file (index.html) and opening it with your browser, however there are small aspects of Monogatari that work better when served through a web server. You don't need anything fancy for this, in fact there's a perfeclty fine web server you can [download from the Chrome Store](https://chrome.google.com/webstore/detail/web-server-for-chrome/ofhbbkphhbklhfoeikjpcbhemlocgigb)

As previously mentioned, the use of a web server is completely optional, you can just open your game with the browser as a file and it will run just fine, the web server will allow you to test features such as the Service Workers, needed for Monogatari's offline support and asset preloading.

### Download the latest release
Once you've got your environment set up, it's time to download Monogatari. You can get the last release from [here](https://github.com/Monogatari/Monogatari/releases/latest).

Download the .zip file and unzip it, inside you'll find your game files, now, what are those files and what are they used for?


### Directories
You'll find some directories, here is what you should use them for. 

| Directory | Contains |
| ------------- | ------------- |
| audio | Audio files (Music, voice and sounds). |
| error | Custom error pages, you may modify those as you wish. |
| fonts | Font Awesome by default,every other font should be placed here as well |
| style | CSS files for your project (CSS defines the look and style of your game). |
| img | All the images for your project (UI, Backgrounds, characters etc.) |
| js | All the things that'll make your VN work |

#### Root Directory
Inside the main directory you'll find some pretty useful files.

| Directory | Contains |
| index.html | This is your main file, open this file in a browser and there's your game! |
| electron.js | File used as an entry point for electron in case you are using it to make your game for the desktop. |
| service-worker.js | This file defines your service worker, used for asset preloading and caching. |

More about what to do and how to use this specific files will come later as you read the documentation.

#### JS Directory

JavaScript is the programming language you'll be using in Monogatari, it is what makes all your game work. In general, you'll be using the **marked** files, the files with a ˋ.min.jsˋ extension are third party libraries used for the engine and other functionality, you should leave them untouched.


| File | Contains |
| ------------- | ------------- |
| **main.js** | If you want to add more javascript, this is the file to do it! |
| **options.js** | Initial settings of your game and engine settings. |
| **script.js** | The main script of your game. (Here's where your story, characters, images etc are declared) |
| **strings.js** | UI translations used for internationalization.|
| monogatari.js | The engine itself, you may modify it but only if you know what you're doing. |
| artemis.min.js | Aegis JavaScript library for DOM manipulation used in the engine. |
| jquery.min.js | jQuery library for user defined functionality. |
| particles.min.js | Javascript library for particles animations. |
| typed.min.js | Javascript library for the text typing animation. |

#### Style Directory
CSS is the markup language used to style your game, from setting colors to improving the appearance, CSS is what will allow you do them all. As before, you are you'll be using the **marked** files, the files with a ˋ.min.cssˋ extension are third party libraries used for the engine and other functionality, you should leave them untouched.


| File | Contains |
| ------------- | ------------- |
| **main.css** | Add your styling in this file. |
| monogatari.css | File with the initial styling of Monogatari, any midifications should be done in the main.css file. |
| csshake.min.css | CSS Shake Animations Library. |
| animate.min.css | CSS Animations Library. |
| font-awesome.min.css | CSS of Font Awesome. |
| normalize.min.css | CSS Normalizer |

### Workflow

Ok so now you have the environment set up, you have some idea on what the files you got are for so how can you start developing your game?

1. Try the game first, open the index.html file inside the directory you just unzipped and play the sample game through.
2. Once you've played it once, open the directory (the one you unzipped) with the editor you chose to start making changes.
3. Open the script.js file with your editor, find the variable called ˋscriptˋ, as you'll see, all the dialogs you just saw are just a simple list in there. More information can be found in [the documentation](https://monogatari.io/documentation/script/text/).
4. Change one of the dialogs, save the file and reload the game (just like you reload a website).
5. Play it again and you'll see the dialog changed just like you made it. 
6. Now try adding more dialog to it and you'll quickly get how things are done.
7. Once you've gotten yourself used to adding dialogs, [add a scene](https://monogatari.io/documentation/script/scenes/) as a challenge, that means you'll have to add your image file to the ˋimg/scenes/ directoryˋ, more instructions are on the link.


If you manage to do all that, congratulations! You just made your first game and are probably more familiarized with the workflow you'll be using, just make changes, save, reload, try and repeat!



### Getting Help

While this documentation covers many parts of Monogatari's functioning, it does not cover everything you could actually do with it, remember, your VN is a website now and that means the posibilities are endless. Everything you've seen on a website before can be done in your game.

But how to look out for help on doing this things? Well, another benefit of your game being a website is: There is lots and lots of tutorials and documention out there! 

If you google something, for example if you want something to happen when someone clicks an image, you can google it as "javascript click image", there's no need to look for a Monogatari-specific answer, everything that applies to a website also applies for Monogatari, even the step-by-step tutorials on web development are useful to get you started.

But of course, you are not alone! If you have any doubt, problem or just want some help please contact me, I'll be glad to help in any way I can. Even though Monogatari is simple enough and you can find many resources online, I know it can be hard to get started and sometimes the documentation is not clear enough, so really, contact me anytime! 

You can use my <a class="mailto" href="diego(at)hyuchia(dot)com" > email</a>, DM me at [Twitter](https://twitter.com/Hyuchia), contact me through [Google+](https://plus.google.com/+HyuchiaDiego/) or Hangouts and [Mastodon](https://mastodon.social/@HyuchiaDiego) as well.

If you like Monogatari and would like to support it's creation you can do so by supporting me via [Patreon](https://www.patreon.com/Hyuchia), you can even get the personalized support reward for Monogatari (which is something I do for free if you contact me as previously mentioned but making a pledge through Patreon shows your support and really helps the project :) )
