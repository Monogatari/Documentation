---
description: Show a character's sprite
---

# Show Character

## Description

```
'show character <character_id> <sprite_id> [at [class]] [with [animations] [classes] [properties]]'
```

The character action allows you to display a character's sprite. For other kind of images, take a look at the [show image action](show-image.md).

**Action ID**: `Show::Character`

**Reversible**: Yes

**Requires User Interaction**: No

## Properties

These are special properties/classes that can be used when showing a character:

| Name              | Description                                                                                                                       |
| ----------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| `duration`        | Duration affects the `animation-duration` CSS property so you can change the duration of any animations applied to the character. |
| `move`            | With this class, the character will move nicely from one position to another one.                                                 |
| `transition`      | Transition affects the `transition-duration` CSS property so you can change the duration of the transition for the `move` class.  |
| `end-<className>` | When using this property, the provided class will be added to the sprite when it gets changed.                                    |

## Examples

Remember every character image must be declared in the characters object.

```
'show character e normal at center with fadeIn',
```

The [animation](https://daneden.github.io/animate.css/) is completely optional, and if a position is not given, it will show in the center by default.

```
'show character e normal',
'show character e normal with fadeIn',
```

### Exit Animations

New to version 2.0: You can now also set an animation that will play when the character is removed or replaced.

```
show character <character_id> <sprite_id> [at [class]] [with [animation] [end-[animation]] [classes]]
```

### Duration

This is useful if you want to smoothly transition the same character's sprites, such as this example involving crossfades.

The following code will show the character with a `fadeIn` animation that will take 20 seconds to complete.

```
	"Hello",
	"show character s Normal at center with fadeIn end-fadeOut",
	"s Hi theeeeere.",
	"show character s Happy at center with fadeIn end-fadeOut",
	"I'm happy now, and my smile just faded onto my face.",
	"show character s Normal at center with fadeIn",
	"Normal."
```

```javascript
'show character e normal with fadeIn duration 20s'
```

### End Animations

End animations are a way of preparing an animation to happen whenever a sprite gets changed, the following code will show the character first and when it reaches the next line, the character will fade out while the new sprite fades in.

```javascript
'show character e normal with end-fadeOut',
'show character e happy with fadeIn'
```
