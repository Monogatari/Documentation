# Characters

Characters are the people who speak and appear in your visual novel. Each character has a unique identifier used in scripts.

## Basic Definition

```javascript
monogatari.characters({
    'e': {
        name: 'Evelyn',
        color: '#00bfff'
    }
});
```

## Character Properties

| Property | Type | Description |
| :--- | :--- | :--- |
| `name` | `string` | Display name shown in the text box |
| `color` | `string` | Color for the character's name (hex, rgb, or rgba) |
| `directory` | `string` | Subdirectory in `assets/characters/` for sprite images |
| `sprites` | `object` | Maps sprite identifiers to image filenames |
| `expressions` | `object` | Maps expression identifiers to side images |
| `default_expression` | `string` | Default expression to show when speaking |
| `type_animation` | `boolean` | Enable/disable typewriter animation for this character |
| `nvl` | `boolean` | Use NVL (novel) mode for this character's dialog |

## Complete Example

```javascript
monogatari.characters({
    'e': {
        name: 'Evelyn',
        color: '#00bfff',
        directory: 'evelyn',
        sprites: {
            normal: 'normal.png',
            happy: 'happy.png',
            sad: 'sad.png',
            angry: 'angry.png'
        },
        expressions: {
            normal: 'face_normal.png',
            happy: 'face_happy.png'
        },
        default_expression: 'normal'
    },
    'y': {
        name: 'Yui',
        color: '#ff6b9d',
        directory: 'yui',
        sprites: {
            normal: 'normal.png',
            surprised: 'surprised.png'
        },
        nvl: true  // This character uses NVL mode
    }
});
```

## Directory Structure

Character sprites are loaded from `assets/characters/`. If a `directory` is specified, sprites are loaded from that subdirectory:

```
assets/
└── characters/
    ├── evelyn/           # e.directory = 'evelyn'
    │   ├── normal.png
    │   ├── happy.png
    │   └── face_normal.png
    └── yui/              # y.directory = 'yui'
        ├── normal.png
        └── surprised.png
```

If no `directory` is specified, sprites are loaded directly from `assets/characters/`.

## Using Characters

### In Dialog

Use the character identifier to make them speak:

```javascript
'e Hello! My name is Evelyn.',
'y Nice to meet you!'
```

### With Expressions

Add an expression after a colon to show a side image:

```javascript
'e:happy I\'m so glad to see you!'
```

### Showing Sprites

Display characters on screen using the show command:

```javascript
'show character e normal at center with fadeIn'
```

See [Show Character](../script-actions/characters.md) for full details.

## Experimental: Layered Sprites

> [!WARNING]
> Requires `ExperimentalFeatures` to be enabled.

Characters can use layered sprites for paper-doll systems:

```javascript
monogatari.characters({
    'y': {
        name: 'Yui',
        directory: 'yui',
        layers: ['base', 'clothes', 'face', 'accessories'],
        layer_assets: {
            base: {
                body: 'base_body.png'
            },
            clothes: {
                uniform: 'clothes_uniform.png',
                casual: 'clothes_casual.png'
            },
            face: {
                happy: 'face_happy.png',
                sad: 'face_sad.png'
            },
            accessories: {
                glasses: 'glasses.png'
            }
        },
        sprites: {
            normal: 'normal.png'  // Fallback sprite
        }
    }
});
```

See [Character Layers](../script-actions/character-layers.md) for usage details.

## Legacy Property Names

For backwards compatibility, uppercase property names are still supported:

| Legacy | Modern |
| :--- | :--- |
| `Name` | `name` |
| `Color` | `color` |
| `Directory` | `directory` |
| `Images` | `sprites` |
| `Face` | Part of `expressions` |
| `Side` | `expressions` |
| `TypeAnimation` | `type_animation` |

**Recommended**: Use the modern lowercase property names in new projects.

## Related

- [Show Character](../script-actions/characters.md) - Display characters on screen
- [Hide Character](../script-actions/hide-character.md) - Remove characters from screen
- [Character Layers](../script-actions/character-layers.md) - Control individual sprite layers
- [Dialogs](../script-actions/dialogs.md) - Character dialog syntax
