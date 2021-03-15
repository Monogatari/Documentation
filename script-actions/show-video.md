# Show Video

## Description

```javascript
'show video <video_id> <mode> [with [properties]]'
```

The video action allows you to show videos on your novel in different modes.

**Action ID**: Video

**Reversible**: Yes

**Requires User Interaction**: No, unless the close property is not given, then the user will have to click once the video is over to advance.

## Parameters

<table>
  <thead>
    <tr>
      <th style="text-align:left">Name</th>
      <th style="text-align:left">Type</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">mode</td>
      <td style="text-align:left"><code>string</code>
      </td>
      <td style="text-align:left">
        <p>Defines what way you want to show the video like.</p>
        <p>Possible Values:</p>
        <ul>
          <li><code>modal</code> - Shows the video as a</li>
          <li><code>immersive</code> - Shows the video covering the full game screen</li>
          <li><code>background</code> - Shows the video as a background for your characters</li>
          <li><code>fullscreen</code> - Attempts to show the video in full screen, if
            permission is denied, it will fallback to the <code>immersive</code> mode.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">video_id</td>
      <td style="text-align:left"><code>string</code>
      </td>
      <td style="text-align:left">The ID of a video asset previously defined.</td>
    </tr>
  </tbody>
</table>

### Properties

The following is a comprehensive list of the properties available for you to modify certain behaviors of the video action.

| Name | Type | Description |
| :--- | :--- | :--- |
| controls | `No value required` | Optional. Adding this property will make the video controls \(play, pause, seeking\) visible for the player. |
| close | `No value required` | Optional. Adding this property will make the video close itself once it's over. |
| loop | `No value required` | Optional. Adding this property will make the video loop. The `close` property will not have any effect if the `loop` property is added. |

## Assets Declarations

To play a video, you must first add the file to your **`assets/video/`** directory and then declare it. To do so, Monogatari has an has a function that will let you declare all kinds of assets for your game.

```javascript
Monogatari.assets ('videos', {
    '<video_id>': 'videoFileName'
});
```

### Supported Formats

Each browser has it's own format compatibility. **MP4** however is the format supported by most browsers.

If you wish to use other formats, you can check a [compatibility table](https://developer.mozilla.org/en-US/docs/Web/HTML/Supported_media_formats#Browser_compatibility) to discover what browsers will be able to play it.

## Examples

{% tabs %}
{% tab title="Script" %}
```javascript
Monogatari.script ({
    'Start': [
        'show video flowerTimelapse modal'
        'end'
    ]
});
```
{% endtab %}

{% tab title="Video Assets" %}
```javascript
Monogatari.assets ('video', {
    '<video_id>': 'videoFileName'
});
```
{% endtab %}
{% endtabs %}

