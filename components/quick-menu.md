# Quick Menu

## Description

```
<quick-menu></quick-menu>
```

The quick menu is the small menu rendered in the bottom of the screen, or on the top if you're in mobile. It's a menu that allows access to certain features during the game such as saving, loading, showing the log etc.  
  
The quick menu will render each of the buttons it has on its global configuration

## Configuration

#### Buttons





## Methods

#### Add Button

```
static addButton ({ string, icon, data, ... }): void
```

Adds a button to the end of the menu.

**Example**

```
monogatari.component ('quick-menu').addButton ({
	string: 'Stats',
	icon: 'fas fa-tasks',
	data: {
		action: 'show-stats'
	}
});
```

#### Add Button After

```
static addButtonAfter (after: string, { string, icon, data, ... }): void
```

Adds a button immediately after the button that has the string specified in the `after` argument.

**Example**

The following sample will add the button after the `Back` button

```
monogatari.component ('quick-menu').addButtonAfter ('Back', {
	string: 'Stats',
	icon: 'fas fa-tasks',
	data: {
		action: 'show-stats'
	}
});
```

#### Add Button Before

```
static addButtonBefore (before: string, { string, icon, data, ... }): void
```

Adds a button immediately before the button that has the string specified in the `before` argument.

**Example**

The following sample will add the button before the `Back` button

```
monogatari.component ('quick-menu').addButtonBefore ('Back', {
	string: 'Stats',
	icon: 'fas fa-tasks',
	data: {
		action: 'show-stats'
	}
});
```

