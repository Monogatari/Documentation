# Quick Menu

## Description

```markup
<quick-menu></quick-menu>
```

The quick menu is the small menu rendered in the bottom of the screen, or on the top if you're in mobile. It's a menu that allows access to certain features during the game such as saving, loading, showing the log etc.  
  
The quick menu will render each of the buttons it has on its global configuration

## Configuration

#### Buttons





## Methods

#### Add Button

```javascript
static addButton ({ string, icon, data, ... }): void
```

Adds a button to the end of the menu.

**Example**

```javascript
monogatari.component ('quick-menu').addButton ({
	string: 'Stats',
	icon: 'fas fa-tasks',
	data: {
		action: 'show-stats'
	}
});
```



