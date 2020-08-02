# Events

Monogatari has a lot of useful events that fire when certain engine events happen. These can be used to run your own custom functions with `monogatari.on()`. For example:

```javascript
monogatari.on ('didLoadGame', () => {
  // Something here
});
```

This function would run after loading any save file.

Below is an in-progress list of all events Monogatari has.

## Initialization, Setup, and Binding

| Event | Description | Details |
| :--- | :--- | :--- |
| willInit |  |  |
| willSetup |  |  |
| didSetup |  |  |
| willBind |  |  |
| didBind |  |  |
| didInit |  |  |

## Asset Preloading

| Event | Description | Details |
| :--- | :--- | :--- |
| willPreloadAssets |  |  |
| assetLoaded |  |  |
| assetQueued |  |  |
| didPreloadAssets |  |  |

## Actions

| Event | Description | Details |
| :--- | :--- | :--- |
| willRunAction |  |  |
| didRunAction |  |  |
| willRevertAction |  |  |
| didRevertAction |  |  |

## Configurations

|  |  |
| :--- | :--- |
| configurationElementWillUpdate |  |
| configurationElementUpdate::&lt;Options.js Key&gt; |  |
| configurationElementDidUpdate |  |

## Localization

| Event | Description | Details |
| :--- | :--- | :--- |
| willLocalize |  |  |
| didLocalize |  |  |

## Savefile Loading

| Event | Description | Details |
| :--- | :--- | :--- |
| willLoadGame | Event fires at the start of a savefile load | After the player clicks to load the game but before the game finishes loading. |
| didLoadGame | Event fires after a savefile load | After a save file has finished loading and all storage variable are set, but before anything is drawn to the screen and before players have control. |

## Other:

| Event | Description | Details |
| :--- | :--- | :--- |
| didFinishTyping | Event fires after dialog text finishes | After every line of dialog in Monogatari's typewriter animation finishes and the player is able to click to get a new line. This includes at the end of the animation, as well as after clicking to skip the animation, or after every fed line if typewriter animation is disabled. |
|  |  |  |



