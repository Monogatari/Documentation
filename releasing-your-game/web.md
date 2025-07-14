# Web

Monogatari was built with this in mind, releasing your game online and thus making it available to play almost anywhere! To release your game online, you should first take care of the following steps.

#### Complete your Meta Tags

Inside your `index.html` file, you'll notice there's a lot of meta tags, every single one of them have the purpose of improving your game SEO so it comes up in search result, make social sharing better and improve the experience on mobile devices. Filling them up is not necessary for your game to work but when releasing it online, failing to do so may result in a poor experience for your players.

Many come already pre-filled but others are for you to fill in, in the case of all the icon files, since v1.3.2 Monogatari provides placeholder icons inside the `img/icons/` directory, be sure to replace those with your own as well as the `favicon.ico` file before releasing your game. Here is the section of meta tags you'll find and that need to be filled in case they aren't already:

```markup
    <title></title> <!--Up to 60-70 Characters. Optimal Format: Primary Keyword - Secondary Keyword | Brand Name-->

    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1, user-scalable=no, maximum-scale=1">
    <meta name="description" content=""> <!--Page description. No longer than 155 characters.-->
    <meta name="keywords" content="">
    <meta name="author" content=""> <!--Name of the author.-->

    <!--Facebook Meta Tags-->
    <meta property="og:image" content="http://" /> <!--URL of Image to show-->
    <meta property="og:description" content="" /> <!--Page Description-->
    <meta property="og:site_name" content="" /> <!--The Name Here-->
    <meta property="og:url" content="http://" /> <!--The Web main URL-->
    <meta property="og:title" content="" /> <!--The Title Here-->

    <!--Google Meta Tags-->
    <meta itemprop="name" content=""> <!--The Name or Title Here-->
    <meta itemprop="description" content=""> <!--Page Description-->
    <meta itemprop="image" content="http://"> <!--URL of Image to show-->

    <!--Twitter Meta Tags - You'll have to validate your website here: https://dev.twitter.com/docs/cards/validation/validator-->
    <meta name="twitter:card" content="summary_large_image"> <!--Content Card Type-->
    <meta name="twitter:domain" content=""> <!--Your web's domain-->
    <meta name="twitter:site" content="@"> <!--@publisher-->
    <meta name="twitter:title" content=""> <!--Page Title-->
    <meta name="twitter:description" content=""> <!--Page description less than 200 characters-->
    <meta name="twitter:creator" content="@"> <!--@author-->
    <meta name="twitter:image:src" content="http://"> <!--URL of Image to show-->

    <!--Android Meta Tags-->
    <meta name="mobile-web-app-capable" content="yes">
    <link rel="icon" sizes="192x192" href="img/icons/icon_192x192.png"> <!--192 x 192 Icon-->
    <link rel="icon" sizes="128x128" href="img/icons/icon_128x128.png"> <!--128 x 128 Icon-->

    <!--Apple Meta Tags-->
    <meta name="apple-mobile-web-app-title" content=""> <!--App Title or Name-->
    <meta name="apple-mobile-web-app-capable" content="yes">
    <meta name="apple-mobile-web-app-status-bar-style" content="black-translucent"> <!--Styling for the iOS Status Bar-->
    <link rel="apple-touch-icon" href="img/icons/icon_60x60.png"> <!--60 x 60 Icon-->
    <link rel="apple-touch-icon" sizes="76x76" href="img/icons/icon_76x76.png"> <!--76 x 76 Icon-->
    <link rel="apple-touch-icon" sizes="120x120" href="img/icons/icon_120x120.png"> <!--120 x 120 Icon-->
    <link rel="apple-touch-icon" sizes="152x152" href="img/icons/icon_152x152.png"> <!--152 x 152 Icon-->
    <link rel="apple-touch-icon" sizes="152x152" href="img/icons/icon_167x167.png"> <!--167 x 167 Icon-->
    <link rel="apple-touch-icon" sizes="152x152" href="img/icons/icon_180x180.png"> <!--180 x 180 Icon-->

    <!--Microsoft Tags-->
    <meta name="msapplication-TileColor" content=""> <!--Color of the tile on Windows. In hexadecimal format-->
    <meta name="application-name" content="" /> <!-- App Title -->
    <meta name="msapplication-tooltip" content="" /> <!--Small text on hover-->
    <meta name="msapplication-starturl" content="http://" /> <!-- URL to start in -->
    <meta name="msapplication-square70x70logo" content="img/icons/icon_70x70.png" /> <!--Image for Tile 70x70-->
    <meta name="msapplication-square150x150logo" content="img/icons/icon_150x150.png" /> <!--Image for Tile 150x150-->
    <meta name="msapplication-wide310x150logo" content="img/icons/icon_310x150.png" /> <!--Image for Tile 310x150-->
    <meta name="msapplication-square310x310logo" content="img/icons/icon_310x310.png" /> <!--Image for Tile 310x310-->

    <link rel="publisher" href=""> <!--Publisher's Google+ URL-->

    <meta name="theme-color" content=""><!--Theme color for browsers in hexadecimal format.-->

    <link rel="shortcut icon" href="img/favicon.ico" /> <!--Favicon. Good tool for creating one: http://xiconeditor.com/ Create all sizes.-->
    <link rel="canonical" href=""> <!--Canonical URL of your webpage-->
```

#### Optimize your images

Optimizing your images is imperative to provide a better experience, we all hate when pages take a lot of time to load, even when using the preload features built in on Monogatari, optimizing your images will provide a better experience, the method you choose to do so is entirely yours to pick.

#### Improve Asset Loading

To improve asset loading and enable offline playing, you'll have to complete the files list you need to save in the cache for your game to be able to work, information about this can be found in the [Asset Preload Configuration](https://monogatari.io/documentation/configuration/asset-preload/).

#### Improve the Mobile experience

A `manifest.json` file is shipped on Monogatari since v1.3.2, this file is needed to provide a better mobile experience, specifically it's another requirement to transform your app in a [Progressive Web App](https://en.wikipedia.org/wiki/Progressive_web_app) which will enable a great experience for your users, specially if they [add your game to their home screen](https://www.howtogeek.com/196087/how-to-add-websites-to-the-home-screen-on-any-smartphone-or-tablet/) which you should encourage! adding it to home screen will show your game icon just as with other app, then show a splash screen when loaded using the `background_color` and icons defined in your `mainfest.json` file and if you've [set up correctly your service worker cache](https://monogatari.io/documentation/configuration/asset-preload/), it will also be possible to play it offline, making it work almost like a native mobile app, an experience your players will truly love.

Inside this file you'll only need to pay attention to four properties:

```javascript
"short_name": "Monogatari", // Maximum 12 characters
"name": "Monogatari Visual Novel", // Maximum 45 characters
"background_color": "#F7F7F7", // Background color for the Splash Screen
"theme_color": "#F7F7F7", // General theme color for the browser
```

For more information about the manifest and what every property does, [check this site](https://developer.mozilla.org/en-US/docs/Web/Manifest).

#### Upload your game
