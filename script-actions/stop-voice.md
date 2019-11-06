# Stop Voice

## Description

```
'stop voice [voice_id] [with [properties]]'
```

The stop voice action will let you stop either all voices currently playing or only one in specific. To learn more about voices, read the[ Play Voice documentation](play-voice.md).

**Action ID**: `Voice::Stop`

**Reversible**: Yes

**Requires User Interaction**: No

## Parameters

| Name | Type | Description |
| :--- | :--- | :--- |
| voice\_id | `string` | Optional. The name of the specific voice you want to stop. |
| properties | `string` | Optional. A list of comma separated properties with their respective value. |

### Properties

The following is a comprehensive list of the properties available for you to modify certain behaviors of the stop voice action.

| Name | Type | Description |
| :--- | :--- | :--- |
| fade | `number` | The fade property let's you add a fade out effect to the voice, it accepts a time in seconds, representing how much time you want it to take until the voice volume is zero. |

## Examples

### Stop a specific Voice

The following will stop a specific voice, identified by it's name.

{% tabs %}
{% tab title="Script" %}
```
Monogatari.script ({
    'Start': [
        'play voice dialog_002 with loop',
        'The previous voice will be repeating itself over and over',
        'play voice dialog_001',
        'Two voices are currently playing',
        'stop voice dialog_002',
        'Now the first one has stopped and the second one will stop as soon as it ends',
        'end'
    ]
});
```
{% endtab %}

{% tab title="Voice Assets" %}
```
Monogatari.assets ('voice', {
    'dialog_001': 'dialog_file_1.mp3',
    'dialog_002': 'dialog_file_2.mp3'
});
```
{% endtab %}
{% endtabs %}

### Stop all Voices

The following will stop all sounds currently playing.

{% tabs %}
{% tab title="Script" %}
```
Monogatari.script ({
    'Start': [
        'play voice dialog_002 with loop',
        'The previous voice will be repeating itself over and over',
        'play voice dialog_001',
        'Two voices are currently playing',
        'stop voice',
        'No voice is playing now',
        'end'
    ]
});
```
{% endtab %}

{% tab title="Voice Assets" %}
```
Monogatari.assets ('voice', {
    'dialog_001': 'dialog_file_1.mp3',
    'dialog_002': 'dialog_file_2.mp3'
});
```
{% endtab %}
{% endtabs %}

### Fade Out Effect

The following will stop the voice, and will use a fade out effect to do so. You can also use a fade out effect when stopping all voices.

{% tabs %}
{% tab title="Script" %}
```
Monogatari.script ({
    'Start': [
        'play voice dialog_002 with loop',
        'The previous voice will be repeating itself over and over',
        'play voice dialog_001',
        'Two voices are currently playing',
        'stop voice dialog_002 with fade 12',
        'Now the first will be slowly stopped and the second one will stop as soon as it ends',
        'end'
    ]
});
```
{% endtab %}

{% tab title="Voice Assets" %}
```
Monogatari.assets ('voice', {
    'dialog_001': 'dialog_file_1.mp3',
    'dialog_002': 'dialog_file_2.mp3'
});
```
{% endtab %}
{% endtabs %}

