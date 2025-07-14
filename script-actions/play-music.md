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

| Name       | Type     | Description                                                                       |
| ---------- | -------- | --------------------------------------------------------------------------------- |
| music\_id  | `string` | The name of the music you want to play. These assets must be declared beforehand. |
| properties | `string` | Optional. A list of comma separated properties with their respective value.       |

### Properties

The following is a comprehensive list of the properties available for you to modify certain behaviors of the play music action.

| Property Name | Type     | Description                                                                                                                                                                                            |
| ------------- | -------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| fade          | `string` | <p>The fade property let's you add a fade in effect to the music, it accepts a time in seconds, representing how much time you want it to take until the music reaches it's maximum volume.</p><p></p> |
| volume        | `number` | The volume property let's you define how high the music will be played.                                                                                                                                |
| loop          | `none`   | Make the music loop. This property does not require any value.                                                                                                                                         |

## Assets Declarations

To play a song, you must first add the file to your **`assets/music/`** directory and then declare it. To do so, Monogatari has an  has a function that will let you declare all kinds of assets for your game.

```javascript
monogatari.assets ('music', {
    '<music_id>': 'musicFileName'
});
```

### Supported Formats

Each browser has it's own format compatibility. **MP3** however is the format supported by every browser.&#x20;

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

The following will set the volume of this song to 73%.&#x20;

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

### Audio Effects

You can apply multiple effects to your audio by specifying them in the properties.

#### Effect Syntax

Effects are specified by their name followed by their parameters:

```javascript
'play music <music_id> with <effect_name> <param1> <param2> ...'
```

#### Available Effects

**Filter**

Applies a Biquad filter (lowpass, highpass, etc.)

**Parameters:**

* `type` - Filter type: `lowpass`, `highpass`, `bandpass`, `notch`, `allpass`, `peaking`, `lowshelf`, `highshelf` (default: `lowpass`)
* `frequency` - Cutoff frequency in Hz (default: `800`)
* `Q` - Quality factor (default: `1`)
* `gain` - Filter gain in dB (default: `0`)

**Example:**

```javascript
'play music mainTheme with filter lowpass 400 2'
```

**Delay**

A simple delay effect with feedback

**Parameters:**

* `time` - Delay time in seconds (default: `0.4`)
* `feedback` - Feedback amount 0-1 (default: `0.5`)
* `mix` - Wet/dry mix 0-1 (default: `0.5`)

**Example:**

```javascript
'play music mainTheme with delay 0.5 0.3 0.7'
```

**Compressor**

Dynamic range compression

**Parameters:**

* `threshold` - Compression threshold in dB (default: `-24`)
* `knee` - Knee width in dB (default: `30`)
* `ratio` - Compression ratio (default: `12`)
* `attack` - Attack time in seconds (default: `0.003`)
* `release` - Release time in seconds (default: `0.25`)

**Example:**

```javascript
'play music mainTheme with compressor -20 20 8 0.01 0.1'
```

**Tremolo**

Modulates the amplitude of the signal

**Parameters:**

* `frequency` - Modulation frequency in Hz (default: `5`)
* `depth` - Modulation depth 0-1 (default: `0.8`)

**Example:**

```javascript
'play music mainTheme with tremolo 3 0.6'
```

**Distortion**

Applies wave-shaping distortion

**Parameters:**

* `amount` - Distortion amount (default: `50`)
* `oversample` - Oversampling: `2x`, `4x`, or `none` (default: `4x`)

**Example:**

```javascript
'play music mainTheme with distortion 30 2x'
```

**Convolution Reverb**

Convolution reverb with a generated impulse response

**Parameters:**

* `seconds` - Reverb duration in seconds (default: `2`)
* `decay` - Decay rate (default: `2`)
* `reverse` - Reverse the impulse response (default: `false`)

**Example:**

```javascript
'play music mainTheme with convreverb 3 1.5'
```

**Bitcrusher**

Reduces bit depth and sample rate of the signal

**Parameters:**

* `bits` - Bit depth 1-16 (default: `4`)
* `frequency` - Sample rate reduction 0-1 (default: `0.1`)

**Example:**

```javascript
'play music mainTheme with bitcrusher 8 0.2'
```

**AutoWah**

An envelope-following filter (auto-wah)

**Parameters:**

* `baseFrequency` - Base frequency in Hz (default: `100`)
* `octaves` - Frequency range in octaves (default: `6`)
* `sensitivity` - Envelope sensitivity 0-1 (default: `0.5`)
* `Q` - Filter Q factor (default: `10`)

**Example:**

```javascript
'play music mainTheme with autowah 200 4 0.7 15'
```

**Panner**

Positions the sound in 3D space

**Parameters:**

* `x` - X position (default: `0`)
* `y` - Y position (default: `0`)
* `z` - Z position (default: `0`)

**Example:**

```javascript
'play music mainTheme with panner 1 0 0'
```

**Phaser**

A sweeping phase-shifting effect

**Parameters:**

* `frequency` - LFO frequency in Hz (default: `0.5`)
* `depth` - Modulation depth in Hz (default: `1000`)
* `feedback` - Feedback amount 0-1 (default: `0.5`)
* `stages` - Number of filter stages (default: `4`)

**Example:**

```javascript
'play music mainTheme with phaser 1 800 0.3 6'
```

**Chorus**

Creates a thicker sound by modulating a delayed signal

**Parameters:**

* `frequency` - LFO frequency in Hz (default: `1.5`)
* `delay` - Delay time in seconds (default: `0.025`)
* `depth` - Modulation depth in seconds (default: `0.002`)
* `mix` - Wet/dry mix 0-1 (default: `0.5`)

**Example:**

```javascript
'play music mainTheme with chorus 2 0.03 0.003 0.6'
```

**Wah**

A sweeping filter effect, like a guitar wah-wah pedal

**Parameters:**

* `baseFrequency` - Base frequency in Hz (default: `350`)
* `Q` - Filter Q factor (default: `15`)
* `depth` - Frequency sweep range in Hz (default: `1500`)
* `frequency` - LFO frequency in Hz (default: `2`)

**Example:**

```javascript
'play music mainTheme with wah 500 20 2000 1'
```

**Ring Modulation**

Ring modulation for creating metallic, bell-like sounds

**Parameters:**

* `frequency` - Modulator frequency in Hz (default: `30`)
* `mix` - Wet/dry mix 0-1 (default: `0.5`)

**Example:**

```javascript
'play music mainTheme with ringmod 50 0.7'
```

**Saturator**

Soft clipping for warmth and harmonics

**Parameters:**

* `drive` - Drive amount (default: `5`)

**Example:**

```javascript
'play music mainTheme with saturator 3'
```

**Limiter**

A hard compressor to prevent signal peaks from exceeding a threshold

**Parameters:**

* `threshold` - Limiting threshold in dB (default: `-1.0`)
* `release` - Release time in seconds (default: `0.05`)

**Example:**

```javascript
'play music mainTheme with limiter -3 0.1'
```

**Fade In/Out Effects**

Built-in fade effects for smooth transitions

**Parameters:**

* `duration` - Fade duration in seconds (default: `1.0`)

**Example:**

```javascript
'play music mainTheme with fadein 2'
'play music mainTheme with fadeout 3'
```

#### Multiple Effects

You can combine multiple effects on a single music track:

```javascript
'play music mainTheme with filter lowpass 600 1.5 delay 0.3 0.4 0.6 tremolo 4 0.5'
```

#### Effect Compatibility

Some effects require AudioWorklet support, which may not be available in all browsers:

* **Bitcrusher** and **AutoWah** require AudioWorklet support
* If AudioWorklet is not available, these effects will fall back to a simple gain node (no effect)
* Other effects use standard Web Audio API nodes and work in all modern browsers

#### AudioPlayer Properties

The AudioPlayer instance provides several useful properties and methods:

**Properties:**

* `isPlaying` - Whether the audio is currently playing
* `isPaused` - Whether the audio is paused
* `paused` - Alias for `isPaused`
* `ended` - Whether the audio has ended
* `hasEnded` - Alias for `ended`
* `duration` - Total duration of the audio in seconds
* `currentTime` - Current playback position in seconds
* `volume` - Current volume (0-1)
* `loop` - Whether the audio loops

**Methods:**

* `play()` - Start playback
* `pause()` - Pause playback
* `stop()` - Stop playback and reset to beginning
* `fadeIn(duration)` - Fade in over specified duration
* `fadeOut(duration)` - Fade out over specified duration

#### Example: Complex Audio Setup

{% tabs %}
{% tab title="Script" %}
```javascript
monogatari.script ({
    'Start': [
        'play music mainTheme with volume 80 loop filter lowpass 400 2 delay 0.5 0.3 0.4',
        'play music ambient with volume 30 filter highpass 200 1 convreverb 4 1.5',
        'Listen to all the effects!',
        'end'
    ]
});
```
{% endtab %}

{% tab title="Music Assets" %}
```javascript
monogatari.assets ('music', {
    'mainTheme': 'mainThemeSong.mp3',
    'ambient': 'ambientMusic.mp3'
});
```
{% endtab %}
{% endtabs %}

This example creates a layered audio experience with:

* A main theme with low-pass filtering, delay, and looping
* An ambient track with high-pass filtering and reverb
