## Details about repo forked from
Dependency|GitHub|ProPlugin|Available Version to Fork
--- | --- | --- | --- 
nativescript-dom|[Link](https://github.com/NathanaelA/nativescript-dom)|[Link](https://www.npmjs.com/package/nativescript-dom)|2.0.5|

## Documentation
<details>
  <summary>Docs</summary>
  
## Installation 
```bash
npm install ConcordanceHealth/nativescript-dom#branch
```

## Usage
To use the  module you just `require()` it:

```js
require("nativescript-dom");
```

**Note:** You do NOT need to keep a reference to it; and you only need to load it once.
It will automatically attach its methods to all the proper classes in the NativeScript library, making it act as if they are built in.

### Methods

#### `getElementById(id)`
#### `getElementsByClassName(className)`
#### `getElementsByTagName(tagName)`

These are globally available! Like their Web DOM counterparts; they return elements based on the critera.

#### `view.getElementById(id)`
#### `view.getElementsByClassName(className)`
#### `view.getElementsByTagName(tagName)`
Like their Web DOM counterparts; returns the children elements based on the critera.

```js
exports.pageLoaded = function(args) {
  var page = args.object;
  var stackLayout = page.getElementsByTagName('StackLayout')[0];
  var button = stackLayout.getElementsByClassName('clickButton')[0];
  button.classList.toggle('hidden');
}
```

#### `view.runAgainstId(id, function(elem) { /* Do something with elem */ })`
#### `view.runAgainstClasses(className, function(elem) { /* Do something with elem */ })`
#### `view.runAgainstTagNames(tag, function(elem) { /* Do something with elem */ })`
This will automatically run your function passing it the elem that it matches; it will call your function multiple times once for each element that matches your selection.

```js
exports.pageLoaded = function(args) {
  var page = args.object;
  page.runAgainstClasses('clickButton', function(elem) {  
      elem.classList.toggle('hidden');
  });
}
```
  
#### `view.classList.add(className, className, ...)`
Add a class to the view's class list at the end

```js
someButton.classList.add('hidden');  // ClassList on this button will be "class1 class2 classx hidden"
```

#### `view.classList.insert(className, className, ...)`
Add a class to the view's class list at the front
```js
someButton.classList.insert('hidden'); // ClassList on this button will be "hidden class1 class2 classx"
```


#### `view.classList.remove(className, className, ...)`
Removes a class from the view's class list
```js
someButton.classList.remove('hidden'); // ClassList would then equal "class1 class2 class3"
```
   
#### `view.classList.toggle(className[, force])`
Toggles a class name
if force = true, will force adding the class name only.     (And won't remove it, but you won't have a second)
if force = false, will force removing the class name only.  (And won't add it)

#### `view.classList.item(index)`
Returns the class name at that location in the class list.

#### `view.classList.contains(className)`
Returns true or false if the class name exists in the class list.
```js
if (someButton.classList.contains('hidden')) {
    someButton.classList.remove('hidden');
} else {
    someButton.classList.add('hidden');
 }

  // someButton.classList.toggle('hidden');    would be equivelent to the 5 lines above.
```

#### TypeScript Global Augmentation
This module ships a file, `dom-global.d.ts`, to enable intellisense and benefit from the TypeScript Typings
add a reference in your `references.d.ts` file. Below is the snippet you can paste into the `references.d.ts` in the root of your app.

<sub>*You may need to restart your IDE for it to resolve the added typings.*</sub>


```xml
/// <reference path="./node_modules/nativescript-dom/dom-global.d.ts" />
```
</details>


## Original Read Me 08/27/2019
<details>
  <summary>OG Read Me</summary>
<a href="https://proplugins.org"><img src="https://proplugins.org/logos/unmaintained.svg" height="30px" width="100%"></a>

# NativeScript-Dom

<p align="center"><a href="https://proplugins.org"><img src="https://proplugins.org/logos/logo.png" width="400"  /></a></p>

We have an awesome, new service in town!   This service provides tested new and upgraded plugins.  All ProPlugins are already known to work with NativeScript 6.x.
If you are interested in getting the latest, known working, and enhanced plugins; check out https://ProPlugins.org -- because I strongly believe in what ProPlugins offers the community all of my development work is being done on the ProPlugins version.

Please feel free to continue to use this version of the plugin, it is now 100% being maintained by **YOU** the community, and as such
I will gladly continue to support the community version by accepting any/all PR's for this plugin and publish it.  I will attempt to verify the PR doesn't have any backdoors; but I won't be doing any testing, so if it is broken it is up to you to send a PR!


## Documentation
The [documentation](src/README.md) for the plugin is located in the [src folder](src).
</details>
