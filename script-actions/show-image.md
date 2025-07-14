---
description: Show an image
---

# Show Image

## Description

```javascript
'show image <resource> [with [animations] [classes]]'
```

The `image` allows you to display an image. For character sprites, take a look at the [show character action](characters.md).

**Action ID**: `Image`

**Reversible**: Yes

**Requires User Interaction**: No

## Examples

In case of images, they can be declared to use an identifier or you can also use the file's name. The root directory for images will always be img.

```javascript
'show image flower center with fadeIn', // If flower is declared
'show image flower.png center with fadeIn' // If flower isn't declared
```
