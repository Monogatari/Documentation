# Audio

Everyone enjoys music while playing and adding some special effects and voices to your characters' dialogs can make the experience even better!

The `Play` action is the way of doing it. You can declare them so they'll have an identifier, if you prefer using the file's name that's ok, just remember that either case they must be in the corresponding directory \(music, voice or sound\) inside the audio directory.

To view the supported formats, you can take a look at [this page](http://www.w3schools.com/html/html5_audio.asp).

### Audio Assets Declarations

```javascript
Monogatari.assets ('music',  {
    'Theme': 'song.mp3'
});

Monogatari.assets ('voice',  {
    'F1': 'f1.mp3'
});

Monogatari.assets ('sound',  {
    'Rain': 'rain.mp3'
});
```

#### 

### Play Music

The general structure for the play action follows the following syntax:

```javascript
'play music <id> [loop] [controls]'
```

With declaration:

```javascript
'play music Theme loop' // If loop isn't there, it will only play once.
```

Without declaration:

```javascript
'play music song.mp3 loop'
```

You can stop or pause an specific music:

```javascript
'stop music Theme'
```

```javascript
'pause music Theme'
```

Or, you can stop or pause all music being played:

```javascript
'stop music'
```

```javascript
'pause music'
```

#### Voice

```javascript
'play voice f1'
```

#### Sound

With declaration:

```javascript
'play sound Rain loop' // If loop isn't there, it will only play once.
```

Without declaration:

```javascript
'play sound rain.mp3 loop'
```

You can also stop a sound with the `'stop'` command.

```javascript
'stop sound'
```

