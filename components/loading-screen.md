---
description: The screen showing the asset preloading progress
---

# Loading Screen

## Description

```markup
<loading-screen></loading-screen>
```

This is the first screen that will be shown if Asset Preloading is enabled on the game's configuration.

**Component tag:** loading-screen

## Component Structure

The following code is this component's initial HTML structure. Remember you can change this structure any time by using the [`template()` component built-in function](../advanced-monogatari-development/components/built-in-functions.md#get-or-modify-the-html-structure).

```markup
<section data-component="loading_screen" data-screen="loading">
	<div data-content="wrapper">
		<h2 data-string="Loading" data-content="title">Loading</h2>
		<progress data-ui="load-progress" value="0" max="100" data-content="progress_bar"></progress>
		<small data-string="LoadingMessage" data-content="message">Wait while the assets are loaded.</small>
	</div>
</section>
```



