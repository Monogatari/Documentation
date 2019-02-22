---
description: Make the player's device vibrate
---

# Vibrate

### Description

```javascript
'vibrate <pattern>'
```

The `vibrate` action allows you to make the player's device vibrate on a given pattern. If this feature is not supported on the player's device, nothing will happen and the game will continue with it's normal flow.

**Action ID**: Vibrate

**Reversible**: Yes

**Requires User Interaction**: No

### Parameters

| Name | Type | Description |
| :--- | :--- | :--- |
| pattern | `numbers` | List of **space separated** times in **milliseconds**. While there's no limit on how large a pattern can be, at least one time is required. |

### Examples

#### Making the device vibrate once during 200ms:

```javascript
Monogatari.script ({
    'Start': [
        'vibrate 200'
        'end'
    ]
});
```

#### Making the device vibrate with a pattern:

```javascript
Monogatari.script ({
    'Start': [
        'vibrate 200 100 150 50 200 300'
        'end'
    ]
});
```

