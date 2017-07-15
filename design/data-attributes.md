## Understanding all the Datas

If you've already seen the HTML, you'll notice many "data" attributes in the elements; this are used by the engine so you may change the structure and using the right datas everything will just work.

This table will resume  the general datas and what are they for.

| Data | Function |
| ------------- | ------------- |
| data-action || All data-actions well... do something, they are handled by the $("[data-action]").click() function in the engine. |
| data-ui || The data-uis are part of the user interface, things that the user will see. |
| data-component || The data-uis are part of the user interface, however the user will not see them. |
| data-menu || The data-menus are the screens and menus of your game. |
| data-background || Put an image url on it and it will apply that image as a background to that element. |
| data-close || Closes another element by it's data-ui name. |
| data-target || This is mainly used for internal functions, just to target the specific media player. |
| data-string || Used for Multilanguage Games, will change the text of the element with the proper translation from the strings.js file. |
| data-jump || Used in choices, to state what a choice will do when it's clicked. |

Now, that gives you some idea of what everything is for, now you need to understand what every one of them is used for.

| Data | Function |
| ------------- | ------------- |
| data-action="open-menu" || Opens the menu/screen from the data-open next to it and closes the others. |
| data-action="back" || While playing, it will go back to the previous statement, while on a menu, it will just go back to the main screen. |
| data-action="close" || Will trigger the close of an element, using the data-close next to it. |
| data-action="close-video" || Closes the Video element. |
| data-action="set-language" || Used for the language setting. |
| data-action="set-volume" || Changes the volume of the element given in the data-target next to it. |
| data-action="jump" || Declares an element that when clicked will make the game jump to the label declared inside it's data-jump. |
| data-jump="[label]" || Declares the label the game will jump to when this data-action="jump" element is clicked. |
| data-component="modal" || Defines a modal window like the one used for the messages. |
| data-ui="inner-menu" || Defines a menu inside another menu/screen. |
| data-ui="slots" || Defines the place where the save and load slots will be displayed. |
| data-ui="text" || Defines the place where the "Say" text and character's name is displayed. |
| data-ui="who" || Defines the place where the character's name is displayed. |
| data-ui="say" || Defines the place where the "Say" text is displayed. |
