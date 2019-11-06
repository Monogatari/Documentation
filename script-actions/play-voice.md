---
description: Play a voice audio file
---

# Play Voice

## Description

```
'play voice <voice_id> [with [properties]]'
```

The `play voice` action let's you, as it name says, play voice files so that you can make your characters speak. You can play as many voices as you want simultaneously.

To stop a voice, check out the [Stop Voice documentation](stop-voice.md).

**Action ID**: `Voice`

**Reversible**: Yes

**Requires User Interaction**: No

## Parameters

| Name | Type | Description |
| :--- | :--- | :--- |
| voice\_id | `string` | The name of the voice file you want to play. These assets must be declared beforehand. |
| properties | `string` | Optional. A list of comma separated properties with their respective value. |

### Properties

The following is a comprehensive list of the properties available for you to modify certain behaviors of this action.

<table>
  <thead>
    <tr>
      <th style="text-align:left">Property Name</th>
      <th style="text-align:left">Type</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">fade</td>
      <td style="text-align:left"><code>string</code>
      </td>
      <td style="text-align:left">
        <p>The fade property let&apos;s you add a fade in effect to the voice, it
          accepts a time in seconds, representing how much time you want it to take
          until the voice reaches it&apos;s maximum volume.</p>
        <p></p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">volume</td>
      <td style="text-align:left"><code>number</code>
      </td>
      <td style="text-align:left">The volume property let&apos;s you define how high the voice will be played.</td>
    </tr>
    <tr>
      <td style="text-align:left">loop</td>
      <td style="text-align:left"><code>none</code>
      </td>
      <td style="text-align:left">Make the voice loop. This property does not require any value.</td>
    </tr>
  </tbody>
</table>## Assets Declarations

To play a voice, you must first add the file to your **`assets/voice/`** directory and then declare it. To do so, Monogatari has an  has a function that will let you declare all kinds of assets for your game.

```
Monogatari.assets ('voice', {
    '<voice_id>': 'voiceFileName'
});
```

### Supported Formats

Each browser has it's own format compatibility. **MP3** however is the format supported by every browser. 

If you wish to use other formats, you can check a [compatibility table](https://developer.mozilla.org/en-US/docs/Web/HTML/Supported_media_formats#Browser_compatibility) to discover what browsers will be able to play it.

## Examples

### Play Voice

The following will play the sound, and once the sound ends, it will simply stop.

{% tabs %}
{% tab title="Script" %}
```
Monogatari.script ({
    'Start': [
        'play voice dialog_001',
        'This is the dialog that the voice file is narrating',
        'end'
    ]
});
```
{% endtab %}

{% tab title="Voice Assets" %}
```
Monogatari.assets ('voice', {
    'dialog_001': 'dialog_file_1.mp3'
});
```
{% endtab %}
{% endtabs %}

### Loop Voice

The following will play the voice file, and once it ends, it will start over on an infinite loop until it is stopped using the [Stop Voice Action](stop-voice.md).

{% tabs %}
{% tab title="Script" %}
```
Monogatari.script ({
    'Start': [
        'play voice dialog_001 with loop',
        'This is the dialog that the voice file is narrating',
        'end'
    ]
});
```
{% endtab %}

{% tab title="Sound Assets" %}
```
Monogatari.assets ('voice', {
    'dialog_001': 'dialog_file_1.mp3'
});
```
{% endtab %}
{% endtabs %}

### Fade In effect

The following will play the voice file, and will use a fade in effect.

{% tabs %}
{% tab title="Script" %}
```
Monogatari.script ({
    'Start': [
        'play voice dialog_001 with fade 3',
        'This is the dialog that the voice file is narrating',
        'end'
    ]
});
```
{% endtab %}

{% tab title="Sound Assets" %}
```
Monogatari.assets ('voice', {
    'dialog_001': 'dialog_file_1.mp3'
});
```
{% endtab %}
{% endtabs %}

### Custom Volume

The following will set the volume of this voice to 73%. 

{% tabs %}
{% tab title="Script" %}
```
Monogatari.script ({
    'Start': [
        'play voice dialog_001 with volume 73',
        'This is the dialog that the voice file is narrating',
        'end'
    ]
});
```
{% endtab %}

{% tab title="Sound Assets" %}
```
Monogatari.assets ('voice', {
    'dialog_001': 'dialog_file_1.mp3'
});
```
{% endtab %}
{% endtabs %}

Please note however, that the user's preferences regarding volumes are always respected, which means that this percentage is taken from the current player preferences, meaning that if the player has set the volume to 50%, the actual volume value for the voice will be the result of:

$$
50 * 0.73 = 36.5%
$$

### All Together

Of course, you can combine all of this properties, and remember the order doesn't really matter, you can write the properties on the order that feels more natural to you.

{% tabs %}
{% tab title="Script" %}
```
Monogatari.script ({
    'Start': [
        'play voice dialog_001 with volume 100 loop fade 20',
        'This is the dialog that the voice file is narrating',
        'end'
    ]
});
```
{% endtab %}

{% tab title="" %}
```
Monogatari.assets ('voice', {
    'dialog_001': 'dialog_file_1.mp3'
});
```
{% endtab %}
{% endtabs %}

