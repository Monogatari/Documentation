# Built-in Functions

Components come with a series of built-in functions that will make it easier to interact with them.

## Modify the HTML structure

```javascript
static template ()
```

This function allows you to either get the HTML structure from a component, or set a new one to it.

### Examples

```javascript
monogatari.component ('main_screen').template (() => {
    return `
        <h1>My Awesome Game</h1>
        <main-menu></main-menu>
    `;
});
```



