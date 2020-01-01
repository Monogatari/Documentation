# Placeholder

## Description

```javascript
'$ <placeholder_name>'
```

A placeholder allows you to save some action to use within your game by placing a placeholder on your script wherever you want to call it. This is particularly useful when you have an action that is repeated multiple times in your game or when loading your script from an external source.

**Action ID**: `Placeholder`

**Reversible**: Depends on the action provided

**Requires User Interaction**: Depends on the action provided

## Parameters

| Name | Type | Description |
| :--- | :--- | :--- |
| `placeholder_name` | `string` | The name with which you saved the action you want to call. |

## Action Declarations

To declare an action placeholder, you need to provide a name for it and a value. The value can be any valid monogatari action.

```javascript
monogatari.$ ('menu', {"Choice":{
	"Text":	"Let's see, what do you want to know about?",
	"Animations":{
		"Text": "Animations",
		"Do": "jump Animations"
	},
	"Media":{
		"Text": "Multimedia",
		"Do": "jump Media"
	},
	"Scripting":{
		"Text": "Scripting",
		"Do": "jump Script"
	},
	"Playing":{
		"Text": "Playing",
		"Do": "jump Playing"
	},
	"Nothing": {
		"Text": "Nothing",
		"Do": "jump Nothing",
		"Condition": function () {
			return storage.playing && storage.media && storage.scripting && storage.animations;
		}
	}
}});
```

## Examples

### Using a Choice in multiple places

The following will declare the placeholder shown above, featuring a choice action. The recommended place to declare all your placeholders is your main.js file. 

```javascript
monogatari.$ ('menu', {"Choice":{
	"Text":	"Let's see, what do you want to know about?",
	"Animations":{
		"Text": "Animations",
		"Do": "jump Animations"
	},
	"Media":{
		"Text": "Multimedia",
		"Do": "jump Media"
	},
	"Scripting":{
		"Text": "Scripting",
		"Do": "jump Script"
	},
	"Playing":{
		"Text": "Playing",
		"Do": "jump Playing"
	},
	"Nothing": {
		"Text": "Nothing",
		"Do": "jump Nothing",
		"Condition": function () {
			return monogatari.storage ('someFlag');
		}
	}
}});
```

And then, whenever you want to use that in your script, you just need to place the following statement, saving a lot of space and making it easier to have the same choice in multiple places:

```javascript
'$ menu'
```

### Dynamic Action Generation

Another great way of using placeholders is generating actions dynamically. To make this happen, be sure that the name you use for your placeholders starts with `_`

The value for your placeholder should be a function that can return any action. Your function will be evaluated before executing it to retrieve the action to run.

{% hint style="danger" %}
**Beware, this is only recommended for advanced users.** When using dynamic action generation, you will be responsible on providing the way to rollback what you did, this means you'll need to save up your own markers in order to know what action you executed before.
{% endhint %}

```javascript
monogatari.$ ('_dialog', function () {
    // Within this function, `this` refers to the Monogatari object.
    
    if (this.storage ().someFlag) {
        return 'y This means the flag was true!';
    } else {
        return 'y This means the flag was false!';
    }
});
```

