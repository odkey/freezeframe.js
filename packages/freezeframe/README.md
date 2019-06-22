# Freezeframe.js

[![npm version](https://badge.fury.io/js/freezeframe.svg)](https://badge.fury.io/js/freezeframe)
![Size](https://img.shields.io/github/size/ctrl-freaks/freezeframe.js/packages/freezeframe/dist/freezeframe.min.js.svg)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)

Freezeframe.js is a library that pauses animated .gifs and enables them to
animate on mouse hover / mouse click / touch event, or manually via class methods.

Version 4.x no longer requires or supports jQuery. If you want to use freezeframe as a jQuery
plugin, check out [freezeframe v3.0.10](https://github.com/ctrl-freaks/freezeframe.js/tree/archived/3.0.10).

- [Freezeframe.js](#Freezeframejs)
  - [Examples](#Examples)
  - [Installation](#Installation)
    - [npm](#npm)
    - [yarn](#yarn)
    - [CDN](#CDN)
  - [Setup](#Setup)
  - [Usage](#Usage)
  - [Advanced Usage](#Advanced-Usage)
  - [Options Reference](#Options-Reference)
  - [Function Reference](#Function-Reference)
  - [Contributing](#Contributing)
  - [License](#License)
  - [Thanks](#Thanks)

## Examples

[http://ctrl-freaks.github.io/freezeframe.js/](http://ctrl-freaks.github.io/freezeframe.js/)

## Installation

If your project supports ES6 modules or commonjs modules, install via npm or yarn:

### npm

```bash
npm install freezeframe
```

### yarn

```bash
yarn add freezeframe
```

### CDN

If not, you can pull in the library from a CDN:

```html
<script src="https://unpkg.com/freezeframe/dist/freezeframe.min.js"></script>
```

## Setup

Add **freezeframe** as a class name on the .gifs you want processed.  
( You can optionally specify a custom selector as shown in [Advanced Usage](#advanced_usage). )

```html
<img class="freezeframe" src="image.gif" />
```

Add **freezeframe-responsive** as an additional class name to make the .gif responsive.

```html
<img class="freezeframe freezeframe-responsive" src="image.gif" />
```

## Usage

If your environment supports commonjs modules (`require`) or es6 module imports (`import`), you can import freezeframe like so:

```js
// es6 modules
import Freezeframe from 'freezeframe';

// or commonjs
const Freezeframe = require('freezeframe');
```

However, if you are using the CDN version, you can just access the global variable, `Freezeframe`.

✨ Now time to Freeze those frames ✨

```js
new Freezeframe();
```

## Advanced Usage

freezeframe.js exposes public methods to allow for more custom integration. You 
have the option of manually controlling when freezeframe triggers images, adds 
support elements, and attaches event handlers. You can also manually trigger 
and release animation on one image or a group of images. These methods are 
described in detail in the [Function Reference](#function_reference).

*Example: trigger logo .gif and manually trigger / release animation:*

```js
// setup freezeframe instance with custom selector and options

const logo = new Freezeframe('#logo', {
  trigger: false
});

logo.start(); // start animation
logo.stop(); // stop animation
```

## Options Reference

- ### ```selector```

    <code><b>type:</b> string|DOM object</code>  
    <code><b>default</b>: ".freezeframe"</code>  

    The selector used to search for .gifs when the ```trigger()``` function is run.
    Selector may either be passed as the first argument of the Freezeframe constructor, or as a
    property of the options object.

- ### ```trigger```  

    <code><b>type:</b> string | boolean</code>  
    <code><b>default</b>: "hover"</code>  
    <code><b>options</b>: "hover", "click", false</code>  

    The trigger event to start animation for non-touch devices.

- ### ```overlay```  

    <code><b>type:</b> boolean</code>  
    <code><b>default</b>: false</code>  

    Whether or not to display a play icon on top of the paused image.

## Function Reference

- ### ```Freezeframe(options)```  

    Create a new freezeframe object instance.  
    Can be passed options. Strings will be interpreted as the **selector** option.

  ```js
  // Default options
  new Freezeframe();

  // String as selector option
  new Freezeframe('.my-class');

  // Object as options
  const ff = new Freezeframe({
    selector: '.my-class',
    trigger: 'hover',
    overlay: true
  });
  ```

- ### ```start(selector)```

    Start animation, or restarts animation from the first frame if
    the .gif is already animating. Can be filtered by selector.

  ```js
  ff.start();
  ```

- ### ```stop(selector)```

    Stops animation.

  ```js
  ff.stop();
  ```

## Contributing

Assuming you have already read the [instructions](../../#contributing) in the project root:

- First, `cd` into the appropriate package directory

```bash
# start webpack dev server
npm start
```

```bash
# build the project and examples for gh-pages
npm run build
```

Then commit your changes and submit your PR for review.

## License

freezeframe.js is released under the terms of the MIT License.

## Thanks

- [Browserstack - Live, Web-Based Browser Testing](https://www.browserstack.com/)