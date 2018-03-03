## Splitting up your Monogatari Script

Monogatari games are made pretty much by the script you create, that script is all wrapped up in one single variable and file. This may be convenient at first but as your game grows up, the script may start to be a bit too big for it to easily read, it can become somewhat stressful even and in worse cases, it may slow down your text editor while you make changes to it.


In order to prevent this, you can split your script into several files. Spliting your script may also be a good idea when having many branches of your story, when you want to make proofreading somewhat simpler and of course really helpful when your game is available in multiple languages.

This documentation page was Sponsored by [My Awesome Patrons](https://www.patreon.com/Hyuchia), thanks a lot guys!


### So, how to do it?

Figured the best way to show you how to do it was to provide an example project so you can [download it here](https://web.tresorit.com/l#bodWbeyU-QOWNb7Iuo3XZQ). 


Splitting your script is more about splitting labels really, remember that every label is like a chapter or a scene in your visual novel so splitting your game in labels makes a lot of sense, of course splitting those labels in different files makes even more sense. 


Each label has an id that you specify, the initial label (as in the one with which your games always starts) is the one with the "Start" id. You then use the "jump" statements to go from there to any other label you created.


To have a label in another file, you just need to declare it like this:



```javascript
script["OtherLabel"] = [

    "This is another label!"

];

```


That declaration is the same as if you had the following (I'm omitting the contents of the Start label for simplicity):


```javascript
var script = {

    "Start": [...],
   "OtherLabel": [

        "This is another label!"     

    ]

};

```


That means you can declare labels not only in the var script = {...}; code but also from outside of it. `"OtherLabel"` is being used as the id but remember it can be pretty much anything you want.  


Since we are splitting things up, that means the script.js file will not longer be the only place where our story resides. You'll be saving that label (the first code showed in this post) in other file, remember you need to load that file as well, so just add it in your index.html file, right below the line that says:

```html
<script src="js/script.js"></script>
```

Let's suppose you are saving that level on a file with the same name: OtherLabel.js, to load it. Just insert another script tag like this one: 

```html
<script src="js/OtherLabel.js"></script>
```

If everything worked up correctly, you should be able to jump from one label to another even when they are in different files.


Take a look at the sample project from the link above, it will definitely show you what it is all about and you'll probably get a better understanding of it all, it is really simple and can be quite advantageous.


### Wait but what happens if there are too many files now?

Of course you may get to a point ehere there are simply too many files, if you are serving your game online, that can cause a slower load time which is of course not what we want.


For now, the best solution is to copy and paste all the contents of the files you created into a single one. Yes, you can copy and paste them just as they are one after another, the order is not really important in most cases, the only one that truly matters is the script.js file which should always go first.


This would also need to be done if you are obfuscating your code, it's a lot easier to obfuscate just one file than a lot of them.


This solution is of course not ideal, you can find many utilities for concatenating files, some are stand alone programs, some are websites and some are development utilities.


I personally would recommend those development utilities such as [this one](https://www.npmjs.com/package/gulp-concat/) but the problem is that they are not the easier to use and requires you to install other things therefore you may want to stick with the manual solution or find a nice utility that does it.

This is one of the features I'm planning to add to the Monogatari Studio but haven't really got the time to work on it. Nonetheless, I hope you find the file splitting somewhat useful, once you find a nice work flow around it, you'll see how simple it can get!