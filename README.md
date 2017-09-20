# AutoComplete Component

Follows the Material design spec as seen [here](https://material.io/guidelines/components/text-fields.html#text-fields-layout)

Designed to be 100% compatible with [MDC for Web](https://github.com/material-components/material-components-web)

[Component Egineering Outline](https://docs.google.com/document/d/19ZCzqEHSoqN7k47l6PwUXT7zH82gUbCSRFPOJo7DxBw/edit?usp=sharing)

## Example
![Test gif](https://github.com/vandie/mdc-autoComplete/raw/master/images/autocomplete.gif)

[Example usage](https://codepen.io/vandie/pen/jGbgvQ)

## Basic Usage
For basic usage put the autocomplete class in the textfield div and and add the autocomplete span as shown below.
```
<div class="mdc-textfield mdc-autocomplete">
    <input type="text" id="my-textfield" class="mdc-textfield__input">
    <label class="mdc-textfield__label" for="my-textfield">Autocomplete Test</label>
    <span class='mdc-autocomplete__span'></span>
</div>
```

Next you need to initiate the component and requires you to set a search array.
```
var arr = ['blue','red','green']
var x = new autoCompletePrototype(document.querySelector('.mdc-autocomplete'))
x.searchArray = arr;
```

Your autocomplete should now function.

## Better Usage
It's unlikely that you would just want string data in your auto complete. You may (for example) require an avatar to apear when a valid email has been typed in. This can be done using the `searchAttribute` attribute on the mdc-autocomplete div and a slight modification to your array. Example below.
```
<div class="mdc-textfield mdc-autocomplete" searchAttribute='email'>
    <input type="text" id="my-textfield" class="mdc-textfield__input">
    <label class="mdc-textfield__label" for="my-textfield">Autocomplete Test</label>
    <span class='mdc-autocomplete__span'></span>
</div>
```
Then in your initiation of the component, do this instead.
```
var arr = [{email:'eg1@eg.test',avatar:blue.png},{email:'eg2@eg.test',avatar:red.png},{email:'eg3@eg.test',avatar:green.png},{email:'eg4@eg.test',avatar:yellow.png}]

var ac = new autoComplete(document.querySelector('.mdc-autocomplete'))

ac.searchArray = arr
```

You may also like to force the user to use any autocompleted option. This can be done by adding `ForceComplete=true` to the mdc-autocomplete element like so:

```
<div class="mdc-textfield mdc-autocomplete" ForceComplete=true>
    <input type="text" id="my-textfield" class="mdc-textfield__input">
    <label class="mdc-textfield__label" for="my-textfield">Autocomplete Test</label>
    <span class='mdc-autocomplete__span'></span>
</div>
```

## Events
Although there is an event detailed in the engineering outline. It is unfortunatly not yet implemented.

## Theming
Theming requires the scss to be complete (currently not)