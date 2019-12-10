# Save Slot

## Component Structure

The following code is this component's initial HTML structure. Remember you can change this structure any time by using the [`template()` component built-in function](../advanced-monogatari-development/components/built-in-functions.md#get-or-modify-the-html-structure).

```javascript
let background = '';

const hasImage = this.props.image && this.engine.asset ('scenes', this.props.image);

if (hasImage) {
	background = `url(${this.engine.setting ('AssetsPath').root}/${this.engine.setting ('AssetsPath').scenes}/${this.engine.asset ('scenes', this.props.image)})`;
} else if (this.data.game.state.scene) {
	background = this.data.game.state.scene;

	if (background.indexOf (' with ') > -1) {
		background = Text.prefix (' with ', background);
	}

	background = Text.suffix ('show scene', background);

} else if (this.data.game.state.background) {
	background = this.data.game.state.background;

	if (background.indexOf (' with ') > -1) {
		background = Text.prefix (' with ', background);
	}

	background = Text.suffix ('show background', background);
}
return `
	<button data-delete='${this.props.slot}'><span class='fas fa-times'></span></button>
	<small class='badge'>${this.props.name}</small>
	<div data-content="background" style="${hasImage ? 'background-image' : 'background'}: ${background}"></div>
	<figcaption>${moment (this.props.date).format ('MMMM Do YYYY, h:mm:ss a')}</figcaption>
`;
```



