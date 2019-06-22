# Hide Image

## Description

```javascript
'hide image <image_id> [with [animations] [classes]]'
```

The character action allows you to remove an image from the screen.

To show an image, check the [`Show Image action`](show-image.md).

**Action ID**: `Hide::Image`

**Reversible**: Yes

**Requires User Interaction**: No

## Examples

To hide this images, you'll use the hide command as well.

```javascript
'hide image flower', // If flower is declared
'hide image flower.png' // If flower isn't declared
```

You can also hide them with one of the [exit animations](https://daneden.github.io/animate.css/) available.

```javascript
'hide image flower with fadeOut'
```
