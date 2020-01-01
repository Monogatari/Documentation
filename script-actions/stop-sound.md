# Stop Sound

## Description

```
'stop sound [sound_id] [with [properties]]'
```

The stop sound action will let you stop either all sounds currently playing or only one in specific. To learn more about sound, read the[ Play Sound documentation](play-sound.md).

**Action ID**: `Sound::Stop`

**Reversible**: Yes

**Requires User Interaction**: No

## Parameters

| Name | Type | Description |
| :--- | :--- | :--- |
| sound\_id | `string` | Optional. The name of the specific sound you want to stop. |
| properties | `string` | Optional. A list of comma separated properties with their respective value. |

### Properties

The following is a comprehensive list of the properties available for you to modify certain behaviors of the stop sound action.

| Name | Type | Description |
| :--- | :--- | :--- |
| fade | `number` | The fade property let's you add a fade out effect to the sound, it accepts a time in seconds, representing how much time you want it to take until the sound volume is zero. |

## Examples

### Stop a specific Sound

The following will stop a specific sound, identified by it's name.

{% tabs %}
{% tab title="Script" %}
```
Monogatari.script ({
    'Start': [
        'play sound night loop',
        'play sound fireCracks loop',
        'Two sounds are currently playing',
        'stop sound fireCracks',
        'I guess some one put out the fire, only the night sounds are heard now',
        'end'
    ]
});
```
{% endtab %}

{% tab title="Sound Assets" %}
```
Monogatari.assets ('sound', {
    'fireCracks': 'fire-cracks.mp3',
    'night': 'night.mp3'
});
```
{% endtab %}
{% endtabs %}

### Stop all Sounds

The following will stop all sounds currently playing.

{% tabs %}
{% tab title="Script" %}
```
Monogatari.script ({
    'Start': [
        'play sound night loop',
        'play sound fireCracks loop',
        'Two sounds are currently playing',
        'stop sound',
        'It really is a silent night, nothing is heard anymore',
        'end'
    ]
});
```
{% endtab %}

{% tab title="Sound Assets" %}
```
Monogatari.assets ('sound', {
    'fireCracks': 'fire-cracks.mp3',
    'night': 'night.mp3'
});
```
{% endtab %}
{% endtabs %}

### Fade Out Effect

The following will stop the sound, and will use a fade out effect to do so. You can also use a fade out effect when stopping all sounds.

{% tabs %}
{% tab title="Script" %}
```
Monogatari.script ({
    'Start': [
        'play sound night loop',
        'play sound fireCracks loop',
        'Two sounds are currently playing',
        'stop sound fireCracks with fade 12',
        'I guess some one put out the fire, only the night sounds are heard now',
        'end'
    ]
});
```
{% endtab %}

{% tab title="Sound Assets" %}
```
Monogatari.assets ('sound', {
    'fireCracks': 'fire-cracks.mp3',
    'night': 'night.mp3'
});
```
{% endtab %}
{% endtabs %}

