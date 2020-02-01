# Yet another dark/light mode switcher

- It is a custom element wrapper around https://github.com/postcss/postcss-dark-theme-class
- A bit less code than https://github.com/GoogleChromeLabs/dark-mode-toggle/blob/master/src/dark-mode-toggle.mjs
- NO Shadow DOM
- Accessibility based on https://inclusive-components.design/a-theme-switcher/
- and https://www.smashingmagazine.com/2017/09/building-inclusive-toggle-buttons/
- Easily digestable (npm, etc)

## Working with the code
- Clone the repo `git clone ...`
- Install dependencies `npm install`
- Mesh with the code `npm run server`

## Using the code
- In the HTML insert the custom element:
```html
<dark-light-switch
    default=true 
    text-on=on
    text-off=off
    text-legend="dark theme:">
</dark-light-switch>
```
- Include the javascript and the stylesheet as well
```html
<link href=index.css rel=stylesheet>
<script type=module src=index.js></script>
```

## Attributes
You can control aspects of the switcher through attributes:
- default: Indicates a prefered default theme. If the browser supports `prefers-color-scheme` then this value will be ignored and will get the one from the system. Also since the switcher is using the browser's `localstate` to preserve the state this will be effective only the first time a user visits a page with the switcher (consecutive requests will take the value directly from the `localstate`)
- text-on: Allows for I8n of the default string `on`, can be ommited for English sites
- text-off: Allows for I8n of the default string `off`, can be ommited for English sites
- text-legend: Allows for I8n of the default string `dark theme:`, can be ommited for English sites

## Events
- Every time the state is changed a `change` event is ommited from the `dark-light-switch`

## Note
- The switcher will also synchronise to the system events for `prefers-color-scheme`

### Icons from the Font Awesome icon set:
- https://fontawesome.com/icons/sun?style=regular
- https://fontawesome.com/icons/moon?style=solid
