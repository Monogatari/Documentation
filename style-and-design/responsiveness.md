# Responsiveness

Part of what makes Monogatari unique is how it is responsive out of the box, meaning people in all kind of devices with different form factors will be able to play your game.

It is important to note that responsiveness is not the same as simply scaling your game up or down to fit the screen it's being displayed on. Responsiveness actually let's you create different stylings and layouts for different sizes so you can take advantage when there's more space or adapt your elements when it's less.

Adapting to the device is done using CSS media queries.

## Default Screen-Width Breakpoints

```css
/** Extra Small Devices, Phones (480px) **/
@media screen and (min-width : 30em) {}

/** Medium Screens, Phablets (601px) **/
@media screen and (min-width: 37.56255em) {}

/** Medium Devices, Tablets (992px)**/
@media screen and (min-width: 62em) {}

/** HD Screen, Large Devices, Wide Screens, Desktop (1200px) **/
@media screen and (min-width: 75em) {}

/** Full HD Screen, Large Devices, Wide Screens, Large Desktops (1920px) **/
@media screen and (min-width: 120em) {}

/** Retina Screen , Large Devices, Wide Screens(2560px) **/
@media screen and (min-width: 160em) {}

/** 4k Screens, Large Devices, Wide Screens (3840px) **/
@media screen and (min-width: 240em) {}

/** 5k Screens, Large Devices, Wide Screens (5000px) **/
@media screen and (min-width: 312.5em) {}

/** 8k Screens, Large Devices, Wide Screens (8000px) **/
@media screen and (min-width: 500em) {}
```





