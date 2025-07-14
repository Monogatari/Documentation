# Choice Container

## Component Structure

The following code is this component's initial HTML structure. Remember you can change this structure any time by using the [`template()` component built-in function](../building-blocks/components/built-in-functions.md#get-or-modify-the-html-structure).

```javascript
const choices = this.props.choices.map ((choice) => {
	if (typeof choice.Clickable === 'function') {
		return new Promise ((resolve, reject) => {
			this.engine.assertAsync (choice.Clickable, this.engine).then (() => {
				resolve (`<button data-do="${choice.Do}" ${ choice.Class ? `class="${choice.Class}"`: ''} data-choice="${choice._key}">${choice.Text}</button>`);
			}).catch (() => {
				resolve (`<button data-do="${choice.Do}" ${ choice.Class ? `class="${choice.Class}"`: ''} data-choice="${choice._key}" disabled>${choice.Text}</button>`);
			});

		});
	}
	return Promise.resolve (`<button data-do="${choice.Do}" ${ choice.Class ? `class="${choice.Class}"`: ''} data-choice="${choice._key}">${choice.Text}</button>`);
});

return Promise.all (choices).then ((choices) => `
	<div data-content="wrapper">
		${ choices.join('') }
	</div>
`);
```

