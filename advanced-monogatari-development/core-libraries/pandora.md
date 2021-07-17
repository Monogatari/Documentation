---
description: 'Pandora is what allows monogatari to have self contained, custom HTML elements and allows them to have custom functionality.'
---

# Pandora

Pandora is a Web Components library that allows you to create simple and reusable custom HTML elements.

## Components

```javascript
// Create a new Component
class CustomElement extends Pandora.Component {

	constructor () {
		super ();

		// Add a text property
		this.props = {
			text: ''
		};
	}

	render () {
		// When rendered, this component will show an h2 element with the text
		// given on the props.
		return `<h2>${this.props.text}</h2>`;
	}
}

console.log (CustomElement.tag); // custom-element

// Register the custom element with its tag on the window and add the CustomElement
// class as its controller
window.customElements.define (CustomElement.tag, CustomElement);

// Get the custom element from the DOM
const element = document.querySelector ('custom-element');

// Set its text to Hello World!
element.setProps ( {
	text: 'Hello World!'
});

```

## Documentation
You can find alll the documentation for this library at [https://developers.aegisframework.com/pandora/](https://developers.aegisframework.com/pandora/)


## License
This library is released under a [MIT License](./LICENSE)
{"mode":"full","isActive":false}
