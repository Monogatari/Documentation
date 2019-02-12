# Getting Started

**This documentation is still under revision.**

Any text editor should work for creating your game with Monogatari, even Windows NotePad, I recomend you to use [Atom](https://atom.io/) or [Brackets](http://brackets.io/).

#### Understanding the Parts

You'll see many directories and files when you download Monogatari and you need to understand what every file is for.

| Directory | Contains |  |
| :--- | :--- | :--- |
| audio |  | Audio files \(Music, voice and sounds\). |
| error |  | Custom error pages, you may modify those as you wish. |
| fonts |  | Font Awesome by default,every other font should be placed here as well |
| style |  | CSS files for your project. |
| img |  | All the images for your project \(UI, Backgrounds, characters etc.\) |
| js |  | All the things that'll make your VN work |

Inside the js directory...

| File | Contains |  |
| :--- | :--- | :--- |
| main.js |  | If you want to add more javascript, this is the file to do it! |
| options.js |  | Initial settings of your game and engine settings. |
| script.js |  | The main script of your game. \(Here's where your story, characters, images etc are declared\) |
| monogatari.js |  | The engine itself, you may modify it but only if you know what you're doing. |
| plugins.js |  | File for adding plugins. \(Lazy loading, mailto and nice link scroll are added by default\) |
| aegis.js |  | Aegis library used in the engine. |

Inside the style directory...

| File | Contains |  |
| :--- | :--- | :--- |
| main.css |  | Add your styling in this file. |
| monogatari.css |  | File with the initial styling of Monogatari. |
| animate.min.css |  | CSS Animations Library. |
| font-awesome.min.css |  | CSS of Font Awesome. |
| normalize.min.css |  | CSS Normalizer |

