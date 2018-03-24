# Super Context Menu
Customizable context menu based on jQuery

## Getting started
To use Super Context Menu, simply clone or download and include the script and the style in your HTML. 
Super Context Menu requires jQuery to operate properly!

```
<link rel="stylesheet" href="<your folder>/context-menu.min.css">
<script type="application/javascript" src="<your folder>/context-menu.min.js">
```

## Basics
Once included, Super Context Menu provides a superCm object that can be used to customizable context menus.

### Creating a menu
To display the context menu on right click, you can use the `contextmenu` event handler. Inside the handler, invoke `superCm.createMenu` to create the menu as you like. 

The first argument `options` is an array of object that contains the options to be put in the menu, the second argument `event` is the event object from the event handler parameter.

Be sure to invoke `e.preventDefault()` to prevent browser's context menu from appearing.

```
$('#my-div').on('contextmenu', function(e) {
  e.preventDefault();
  superCm.createMenu([...], e);
});
```

### Structuring the menu
The `options` argument accepts an array of object that can be structured as follows:

```
var options = [
  {
    icon: 'fa fa-plus',   //Icon for the option
    label: 'Add a new item',   //Label to be displayed for the option
    action: function(option, contextMenuIndex, optionIndex) {...},   //The callback once clicked
    submenu: [...],   //An array of object for submenus once hovered
    disabled: false   //Disabled status of the option          
  },
  {
    separator: true   //Menu separator
  }
];
```
