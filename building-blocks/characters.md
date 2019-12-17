---
description: 'Learn about characters, their properties and how to create them!'
---

# Characters

## Overview

Characters are probably one of the most important parts of your novel, not only used for displaying them as sprites but also to display their dialogs.

## Properties

<table>
  <thead>
    <tr>
      <th style="text-align:left">Name</th>
      <th style="text-align:left">Type</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><code>name</code>
      </td>
      <td style="text-align:left"><code>string</code>
      </td>
      <td style="text-align:left">Optional. The name that will be shown when this character speaks.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>color</code>
      </td>
      <td style="text-align:left"><code>string</code>
      </td>
      <td style="text-align:left">Optional. A valid <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/color">CSS color</a> which
        will be used to color the character&apos;s name.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>directory</code>
      </td>
      <td style="text-align:left"><code>string</code>
      </td>
      <td style="text-align:left">Optional. Specifies the sub-directory where the sprites and expressions
        images for the character are stored in case they are not in the root <code>assets/characters</code> directory.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>sprites</code>
      </td>
      <td style="text-align:left"><code>Object</code>
      </td>
      <td style="text-align:left">Optional. An object with the identifiers and file names for each <a href="https://developers.monogatari.io/documentation/v/develop/script-actions/characters">sprite</a> available
        for the character.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>default_expression</code>
      </td>
      <td style="text-align:left"><code>string</code>
      </td>
      <td style="text-align:left">Optional. <a href="https://developers.monogatari.io/documentation/v/develop/script-actions/dialogs#side-images">Side image</a> to
        show every time the character speaks.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>expressions</code>
      </td>
      <td style="text-align:left"><code>Object</code>
      </td>
      <td style="text-align:left">Optional. An object with the identifiers and file names for each <a href="https://developers.monogatari.io/documentation/v/develop/script-actions/dialogs#side-images">side expression</a> available
        for the character.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>nvl</code>
      </td>
      <td style="text-align:left"><code>boolean</code>
      </td>
      <td style="text-align:left">
        <p>Optional. Default is <code>false.</code>
        </p>
        <p></p>
        <p>Whether the character&apos;s dialogs should be shown in <a href="https://developers.monogatari.io/documentation/v/develop/script-actions/dialogs#nvl-dialogs">NVL mode</a>.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>type_animation</code>
      </td>
      <td style="text-align:left"><code>boolean</code>
      </td>
      <td style="text-align:left">
        <p>Optional. Default is <code>true</code>.</p>
        <p></p>
        <p>This property indicates whether the typewriter animation should be used
          when the character speaks or not.</p>
      </td>
    </tr>
  </tbody>
</table>## Examples

Declaring characters is really simple, first, you need an identifier, this is what you'll use for the [`dialog`](../script-actions/dialogs.md) and [`show character`](../script-actions/characters.md) actions. We'll choose the identifier y, short for Yui in this tutorial.

```javascript
monogatari.characters ({
    'y': {

    }
});
```

Each character has many properties, like the name that is shown to the player, and the color for it.

```javascript
monogatari.characters ({
    'y': {
        name: 'Yui',
        color: '#00bfff'
    }
});
```

Since we are building visual novels, we also need images for our characters! You need the Directory inside the img directory where your files will be placed, and assign a simple identifier to each file.

```javascript
monogatari.characters ({
    'e': {
        name: 'Evelyn',
        color: '#00bfff', 
        directory: 'Evelyn', // Optional*
        sprites :{ // Images Identifier for the 'Show' statement.
            normal: 'normal.png',
            mad: 'hmph!.png',
            doubt: 'uhh.png',
            disappointed: 'ngggg....png',
            happy: 'hehehehe.png'
        },
        default_expression: 'face.png', // Optional, side image to show every time the character speaks.
        expressions: { // Side images identifiers to show on dialogs
             smiling: 'smiling.png'
        }
    }
});
```

The `directory` attribute is a subdirectory of characters where the images will be pulled, if no `directory` is given, it will be assumed to be the characters directory itself.

