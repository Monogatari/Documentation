---
description: Show a character's sprite
---

# Show Character

## Description

```
'show character <character_id> <sprite_id> [at [class]] [with [animations] [classes]]'
```

The character action allows you to display a character's sprite. For other kind of images, take a look at the [show image action](show-image.md).

**Action ID**: `Show::Character`

**Reversible**: Yes

**Requires User Interaction**: No

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

```text
show character <character_id> <sprite_id> [at [class]] [with [animation] [end-[animation]] [classes]]
```

This is useful if you want to smoothly transition the same character's sprites, such as this example involving crossfades.

```text
	"Hello",
	"show character s Normal at center with fadeIn end-fadeOut",
	"s Hi theeeeere.",
	"show character s Happy at center with fadeIn end-fadeOut",
	"I'm happy now, and my smile just faded onto my face.",
	"show character s Normal at center with fadeIn",
	"Normal."
```

