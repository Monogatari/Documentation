---
description: Wait an amount of time before continuing
---

# Wait

## Description

```javascript
'wait <time>'
```

The `wait` action allows us to make the game wait for a certain amount of `time` before continuing. Once the time has passed, the game will automatically continue to the next statement.

**Action ID**: `Wait`

**Reversible**: Yes

**Requires User Interaction**: No

## Parameters

| Name | Type | Description |
| :--- | :--- | :--- |
| time | `number` | The time in **milliseconds** that you want the game to wait. |

## Examples

```javascript
Monogatari.script ({
    'Start': [
        'Hello there! I want you to wait 5 seconds now',
        'wait 5000',
        'Wow, that was a long time!',
        'end'
    ]
});
```

In this case, the first dialog will be shown, then, when the player clicks to continue, the `wait`  statement will make it wait for 5 seconds before the next dialog is shown.

You may be wondering why it says `5000` instead of just `5` in order to wait for 5 seconds, the reason behind it is that the `wait` action accepts the time in **milliseconds**, therefore we have to make the conversion from seconds to milliseconds for it to work as we want.

