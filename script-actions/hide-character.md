---
description: Remove a character's sprite from screen
---

# Hide Character

## Description

```
'hide character <character_id> [with [animations] [classes]]'
```

The character action allows you to remove a character's sprite from the screen.

To show a character, check the [`Show Character action`](characters.md).

**Action ID**: `Hide::Character`

**Reversible**: Yes

**Requires User Interaction**: No

## Examples

To hide a character, you only need the 'hide' command. Syntax: 'hide \[Character Identifier\] with \[Animation\]'

```
'hide character e'
```

You can also hide them with one of the [exit animations](https://daneden.github.io/animate.css/) available.

```
'hide character e with fadeOut'
```

