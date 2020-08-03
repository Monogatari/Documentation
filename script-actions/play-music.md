---
description: Play music media
---

# Play Music

## Description

```javascript
'play music <music_id> [with [properties]]'
```

The `play music` action let's you, as it name says, play some background music for your game. You can play as many songs as you want simultaneously.

To stop the music, check out the [Stop Music documentation](stop-music.md).

**Action ID**: `Music`

**Reversible**: Yes

**Requires User Interaction**: No

## Parameters

| Name | Type | Description |
| :--- | :--- | :--- |
| music\_id | `string` | The name of the music you want to play. These assets must be declared beforehand. |
| properties | `string` | Optional. A list of comma separated properties with their respective value. |

### Properties

The following is a comprehensive list of the properties available for you to modify certain behaviors of the play music action.

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
        <p>The fade property let&apos;s you add a fade in effect to the music, it
          accepts a time in seconds, representing how much time you want it to take
          until the music reaches it&apos;s maximum volume.</p>
        <p></p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">volume</td>
      <td style="text-align:left"><code>number</code>
      </td>
      <td style="text-align:left">The volume property let&apos;s you define how high the music will be played.</td>
    </tr>
    <tr>
      <td style="text-align:left">loop</td>
      <td style="text-align:left"><code>none</code>
      </td>
      <td style="text-align:left">Make the music loop. This property does not require any value.</td>
    </tr>
  </tbody>
</table>

## Assets Declarations

To play a song, you must first add the file to your **`assets/music/`** directory and then declare it. To do so, Monogatari has an  has a function that will let you declare all kinds of assets for your game.

```javascript
monogatari.assets ('music', {
    '<music_id>': 'musicFileName'
});
```

### Supported Formats

Each browser has it's own format compatibility. **MP3** however is the format supported by every browser. 

If you wish to use other formats, you can check a [compatibility table](https://developer.mozilla.org/en-US/docs/Web/HTML/Supported_media_formats#Browser_compatibility) to discover what browsers will be able to play it.

## Examples

### Play Music

The following will play the song, and once the song ends, it will simply stop.

{% tabs %}
{% tab title="Script" %}
```javascript
monogatari.script ({
    'Start': [
        'play music mainTheme'
        'end'
    ]
});
```
{% endtab %}

{% tab title="Music Assets" %}
```javascript
monogatari.assets ('music', {
    'mainTheme': 'mainThemeSong.mp3'
});
```
{% endtab %}
{% endtabs %}

### Loop Music

The following will play the song, and once the song ends, it will start over on an infinite loop until it is stopped using the [Stop Music Action](stop-music.md).

{% tabs %}
{% tab title="Script" %}
```javascript
monogatari.script ({
    'Start': [
        'play music mainTheme with loop'
        'end'
    ]
});
```
{% endtab %}

{% tab title="Music Assets" %}
```javascript
monogatari.assets ('music', {
    'mainTheme': 'mainThemeSong.mp3'
});
```
{% endtab %}
{% endtabs %}

### Fade In effect

The following will play the song, and will use a fade in effect.

{% tabs %}
{% tab title="Script" %}
```javascript
monogatari.script ({
    'Start': [
        'play music mainTheme with fade 3'
        'end'
    ]
});
```
{% endtab %}

{% tab title="Music Assets" %}
```javascript
monogatari.assets ('music', {
    'mainTheme': 'mainThemeSong.mp3'
});
```
{% endtab %}
{% endtabs %}

### Custom Volume

The following will set the volume of this song to 73%. 

{% tabs %}
{% tab title="Script" %}
```javascript
monogatari.script ({
    'Start': [
        'play music mainTheme with volume 73'
        'end'
    ]
});
```
{% endtab %}

{% tab title="Music Assets" %}
```javascript
monogatari.assets ('music', {
    'mainTheme': 'mainThemeSong.mp3'
});
```
{% endtab %}
{% endtabs %}

Please note however, that the user's preferences regarding volumes are always respected, which means that this percentage is taken from the current player preferences, meaning that if the player has set the volume to 50%, the actual volume value for the song will be the result of:

$$
50 * 0.73 = 36.5%
$$

### All Together

Of course, you can combine all of this properties, and remember the order doesn't really matter, you can write the properties on the order that feels more natural to you.

{% tabs %}
{% tab title="Script" %}
```javascript
monogatari.script ({
    'Start': [
        'play music mainTheme with volume 100 loop fade 20'
        'end'
    ]
});
```
{% endtab %}

{% tab title="Music Assets" %}
```javascript
monogatari.assets ('music', {
    'mainTheme': 'mainThemeSong.mp3'
}
```
{% endtab %}
{% endtabs %}

