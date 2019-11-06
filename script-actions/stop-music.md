---
description: Stop playing music
---

# Stop Music

## Description

```
'stop music [music_id] [with [properties]]'
```

The stop music action will let you stop either all music currently playing or only one in specific. To learn more about music, read the[ Play Music documentation](play-music.md).

**Action ID**: `Music::Stop`

**Reversible**: Yes

**Requires User Interaction**: No

## Parameters

| Name | Type | Description |
| :--- | :--- | :--- |
| music\_id | `string` | Optional. The name of the specific music you want to stop. |
| properties | `string` | Optional. A list of comma separated properties with their respective value. |

### Properties

The following is a comprehensive list of the properties available for you to modify certain behaviors of the stop music action.

| Name | Type | Description |
| :--- | :--- | :--- |
| fade | `number` | The fade property let's you add a fade out effect to the music, it accepts a time in seconds, representing how much time you want it to take until the music volume is zero. |

## Examples

### Stop a specific Music

The following will stop a specific music, identified by it's name.

{% tabs %}
{% tab title="Script" %}
```
Monogatari.script ({
    'Start': [
        'play music mainTheme loop',
        'play music mistery loop',
        'Two songs are currently playing',
        'stop music mainTheme',
        'Only the mistery song is playing now',
        'end'
    ]
});
```
{% endtab %}

{% tab title="Music Assets" %}
```
Monogatari.assets ('music', {
    'mainTheme': 'mainThemeSong.mp3',
    'mistery': 'misterious_song.ogg'
});
```
{% endtab %}
{% endtabs %}

### Stop all Music

The following will stop all music currently playing

{% tabs %}
{% tab title="Script" %}
```
Monogatari.script ({
    'Start': [
        'play music mainTheme loop',
        'play music mistery loop',
        'Two songs are currently playing',
        'stop music',
        'No music is playing anymore',
        'end'
    ]
});
```
{% endtab %}

{% tab title="Music Assets" %}
```
Monogatari.assets ('music', {
    'mainTheme': 'mainThemeSong.mp3',
    'mistery': 'misterious_song.ogg'
});
```
{% endtab %}
{% endtabs %}

### Fade Out Effect

The following will stop the song, and will use a fade out effect to do so. You can also use a fade out effect when stopping all music.

{% tabs %}
{% tab title="Script" %}
```
Monogatari.script ({
    'Start': [
        'play music mainTheme loop',
        'play music mistery loop',
        'Two songs are currently playing',
        'stop music mistery with fade 5',
        'No music is playing anymore',
        'end'
    ]
});
```
{% endtab %}

{% tab title="Music Assets" %}
```
Monogatari.assets ('music', {
    'mainTheme': 'mainThemeSong.mp3',
    'mistery': 'misterious_song.ogg'
});
```
{% endtab %}
{% endtabs %}

