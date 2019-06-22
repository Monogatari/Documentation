# Dialogs

## Description

```javascript
'[character_id][:[expression_id]] <dialog_text>'
```

#### Show Text

The say statement is used... well, for a character to say something. The syntax is as follows:

'\[Character Identifier\] \[Text to Say\]'

```javascript
'e Hi! My name is Evelyn.'
```

It also accepts HTML, so you can show many things in a text like the Font Awesome icons.

```javascript
'e The <span class="fa fa-arrow-left"></span> button is the back button, press it to return to a previous state of the game.',
```

If no character identifier is given, it will be considered as a narration and no name will be shown.

```javascript
'This would be a narrator.'
```

#### Clear the Text

The `'clear'` command sends an empty line of dialog to remove all text on the screen.

```javascript
'clear'
```

The clear command automatically runs the next line without requiring a click from the player. You may want to insert a `'wait'` command immediately after it or something.

#### Side Images

If you've defined the 'Side' property for your characters, adding a list of images to show, you can use them as side images with each dialog, to do so, you should use a format like this one:

```javascript
'e:Smiling Hi! My name is Evelyn.'
```

This assumes you have a Side image called Smiling, which means with every dialog you can specify what side image to use. If you add the 'Face' property then that image will be shown with every dialog without the need of specifying it inside the statement.

## Centered Dialogs

The `'centered'` command is like a special character-id that goes at the beginning of dialog text to display a special floating `<text-box>` that hovers in the very center of the screen.

```javascript
'centered <dialog_text>'
```

The text box that displays `'centered'` text is special. Rather than being inside of a <text-box> tag, it is instead inside of a <centered-dialog> tag.

```html
<centered-dialog class="animated" data-component="centered-dialog">
			<div data-content="wrapper">Here's some more centered text.</div>
		</centered-dialog>
```

While `'centered'` text is visible on screen, the main `<text-box>` is hidden with a CSS `display:none;` attribute.

HTML can be used inside of `'centered'` text the same way in can with normal dialog, so you can use this to display a special image that removes the text box when it displays it, or something similar.

## NVL Dialogs

The `'nvl'` command is similar to the `'centered'` command in that it is used at the beginning of a line of dialog to present a special display.

```javascript
'nvl <dialog_text>'
```

The `'nvl'` text differs from normal Monogatari text in that clicking does not clear the current text off of the screen, and instead leaves it there, feeding consecutive NVL dialogue one at a time as the player clicks.

By default, `'nvl'` text is stylized to fill the entire screen, similar to games like Fate/stay Night, or Radical Dreamers. NVL mode uses the normal <text-box> tag with a CSS Class named `'nvl'`, which you may style as you see fit using CSS.

The NVL mode text box is scrollable, like other text boxes in Monogatari, should there be too much text to display at once.
