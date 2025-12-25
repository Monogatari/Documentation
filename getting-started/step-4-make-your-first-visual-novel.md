---
description: Learn the basic workflow for working on your game
---

# Step 4: Make Your First Visual Novel

Now that you know [what the files are for](step-3-get-familiarized.md), let's start developing your game!

## Your First Game in 7 Steps

### 1. Try the Sample Game

Open the `index.html` file in your browser and play through the sample game. This gives you a feel for what Monogatari can do out of the box.

### 2. Open the Project in Your Editor

Open the entire project directory (the one you unzipped) with your code editor. This lets you see and edit all the files.

### 3. Find the Script

Open `js/script.js` and find the `script` section. You'll see all the dialogs from the sample game are just items in a simple list:

```javascript
monogatari.script({
    'Start': [
        'Hi! Welcome to Monogatari!',
        'This is a sample dialog.',
        'end'
    ]
});
```

### 4. Make Your First Change

Change one of the dialog lines:

```javascript
monogatari.script({
    'Start': [
        'Hello! This is my first visual novel!',
        'I changed this dialog myself!',
        'end'
    ]
});
```

Save the file.

### 5. See Your Changes

Reload the game in your browser (just like refreshing a website). Play through and you'll see your changed dialog!

### 6. Add More Dialog

Try adding more lines to the script:

```javascript
monogatari.script({
    'Start': [
        'Hello! This is my first visual novel!',
        'I changed this dialog myself!',
        'Adding more dialog is this easy!',
        'Just add more strings to the list.',
        'end'
    ]
});
```

Save and reload to see the results.

### 7. Challenge: Add a Scene

Ready for a challenge? Try adding a background scene:

1. Add an image file to `assets/scenes/` (e.g., `myroom.jpg`)
2. Declare the asset in your script:

```javascript
monogatari.assets('scenes', {
    'myroom': 'myroom.jpg'
});
```

3. Use it in your script:

```javascript
monogatari.script({
    'Start': [
        'show scene myroom with fadeIn',
        'Hello! This is my room!',
        'end'
    ]
});
```

## The Development Workflow

You've just learned the basic workflow:

1. **Edit** - Make changes to your files
2. **Save** - Save the files in your editor
3. **Reload** - Refresh the browser
4. **Test** - Play through your changes
5. **Repeat** - Continue iterating!

## What's Next?

Congratulations! You've made your first game! Here's where to go from here:

### Learn the Basics

- [Script & Labels](../building-blocks/script-and-labels.md) - Understand how scripts work
- [Dialogs](../script-actions/dialogs.md) - Master dialog formatting
- [Characters](../script-actions/characters.md) - Add characters to your story

### Add More Features

- [Show Scene](../script-actions/show-scene.md) - Change backgrounds
- [Play Music](../script-actions/play-music.md) - Add background music
- [Choices](../script-actions/choices.md) - Create branching stories

### Customize Your Game

- [Player Preferences](../configuration-options/player-preferences.md) - Configure settings
- [Styling](../style-and-design/classes.md) - Customize the look and feel

## Tips for Success

> [!TIP]
> - Save your work frequently
> - Test changes incrementally (small changes are easier to debug)
> - Use your browser's developer console (F12) to see error messages
> - Keep the documentation handy for reference

## Need Help?

- Check the [FAQ](../f.a.q..md) for common issues
- Visit the [Community Forums](https://community.monogatari.io/) for support
- Browse the rest of this documentation for detailed guides
