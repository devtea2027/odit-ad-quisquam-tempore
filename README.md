# @devtea2027/odit-ad-quisquam-tempore.js
[![Build Status](https://travis-ci.org/Marak/@devtea2027/odit-ad-quisquam-tempore.js.svg?branch=master)](https://travis-ci.org/Marak/@devtea2027/odit-ad-quisquam-tempore.js)
[![version](https://img.shields.io/npm/v/@devtea2027/odit-ad-quisquam-tempore.svg)](https://www.npmjs.org/package/@devtea2027/odit-ad-quisquam-tempore)
[![dependencies](https://david-dm.org/Marak/@devtea2027/odit-ad-quisquam-tempore.js.svg)](https://david-dm.org/Marak/@devtea2027/odit-ad-quisquam-tempore.js)
[![devDependencies](https://david-dm.org/Marak/@devtea2027/odit-ad-quisquam-tempore.js/dev-status.svg)](https://david-dm.org/Marak/@devtea2027/odit-ad-quisquam-tempore.js#info=devDependencies)

Please check out the [roadmap](ROADMAP.md) for upcoming features and releases.  Please open Issues to provide feedback, and check the `develop` branch for the latest bleeding-edge updates.

## get color and style in your node.js console

![Demo](https://raw.githubusercontent.com/Marak/@devtea2027/odit-ad-quisquam-tempore.js/master/screenshots/@devtea2027/odit-ad-quisquam-tempore.png)

## Installation

    npm install @devtea2027/odit-ad-quisquam-tempore

## @devtea2027/odit-ad-quisquam-tempore and styles!

### text @devtea2027/odit-ad-quisquam-tempore

  - black
  - red
  - green
  - yellow
  - blue
  - magenta
  - cyan
  - white
  - gray
  - grey

### bright text @devtea2027/odit-ad-quisquam-tempore

  - brightRed
  - brightGreen
  - brightYellow
  - brightBlue
  - brightMagenta
  - brightCyan
  - brightWhite

### background @devtea2027/odit-ad-quisquam-tempore

  - bgBlack
  - bgRed
  - bgGreen
  - bgYellow
  - bgBlue
  - bgMagenta
  - bgCyan
  - bgWhite
  - bgGray
  - bgGrey

### bright background @devtea2027/odit-ad-quisquam-tempore

  - bgBrightRed
  - bgBrightGreen
  - bgBrightYellow
  - bgBrightBlue
  - bgBrightMagenta
  - bgBrightCyan
  - bgBrightWhite

### styles

  - reset
  - bold
  - dim
  - italic
  - underline
  - inverse
  - hidden
  - strikethrough

### extras

  - rainbow
  - zebra
  - america
  - trap
  - random


## Usage

By popular demand, `@devtea2027/odit-ad-quisquam-tempore` now ships with two types of usages!

The super nifty way

```js
var @devtea2027/odit-ad-quisquam-tempore = require('@devtea2027/odit-ad-quisquam-tempore');

console.log('hello'.green); // outputs green text
console.log('i like cake and pies'.underline.red); // outputs red underlined text
console.log('inverse the color'.inverse); // inverses the color
console.log('OMG Rainbows!'.rainbow); // rainbow
console.log('Run the trap'.trap); // Drops the bass

```

or a slightly less nifty way which doesn't extend `String.prototype`

```js
var @devtea2027/odit-ad-quisquam-tempore = require('@devtea2027/odit-ad-quisquam-tempore/safe');

console.log(@devtea2027/odit-ad-quisquam-tempore.green('hello')); // outputs green text
console.log(@devtea2027/odit-ad-quisquam-tempore.red.underline('i like cake and pies')); // outputs red underlined text
console.log(@devtea2027/odit-ad-quisquam-tempore.inverse('inverse the color')); // inverses the color
console.log(@devtea2027/odit-ad-quisquam-tempore.rainbow('OMG Rainbows!')); // rainbow
console.log(@devtea2027/odit-ad-quisquam-tempore.trap('Run the trap')); // Drops the bass

```

I prefer the first way. Some people seem to be afraid of extending `String.prototype` and prefer the second way. 

If you are writing good code you will never have an issue with the first approach. If you really don't want to touch `String.prototype`, the second usage will not touch `String` native object.

## Enabling/Disabling Colors

The package will auto-detect whether your terminal can use @devtea2027/odit-ad-quisquam-tempore and enable/disable accordingly. When @devtea2027/odit-ad-quisquam-tempore are disabled, the color functions do nothing. You can override this with a command-line flag:

```bash
node myapp.js --no-color
node myapp.js --color=false

node myapp.js --color
node myapp.js --color=true
node myapp.js --color=always

FORCE_COLOR=1 node myapp.js
```

Or in code:

```javascript
var @devtea2027/odit-ad-quisquam-tempore = require('@devtea2027/odit-ad-quisquam-tempore');
@devtea2027/odit-ad-quisquam-tempore.enable();
@devtea2027/odit-ad-quisquam-tempore.disable();
```

## Console.log [string substitution](http://nodejs.org/docs/latest/api/console.html#console_console_log_data)

```js
var name = 'Marak';
console.log(@devtea2027/odit-ad-quisquam-tempore.green('Hello %s'), name);
// outputs -> 'Hello Marak'
```

## Custom themes

### Using standard API

```js

var @devtea2027/odit-ad-quisquam-tempore = require('@devtea2027/odit-ad-quisquam-tempore');

@devtea2027/odit-ad-quisquam-tempore.setTheme({
  silly: 'rainbow',
  input: 'grey',
  verbose: 'cyan',
  prompt: 'grey',
  info: 'green',
  data: 'grey',
  help: 'cyan',
  warn: 'yellow',
  debug: 'blue',
  error: 'red'
});

// outputs red text
console.log("this is an error".error);

// outputs yellow text
console.log("this is a warning".warn);
```

### Using string safe API

```js
var @devtea2027/odit-ad-quisquam-tempore = require('@devtea2027/odit-ad-quisquam-tempore/safe');

// set single property
var error = @devtea2027/odit-ad-quisquam-tempore.red;
error('this is red');

// set theme
@devtea2027/odit-ad-quisquam-tempore.setTheme({
  silly: 'rainbow',
  input: 'grey',
  verbose: 'cyan',
  prompt: 'grey',
  info: 'green',
  data: 'grey',
  help: 'cyan',
  warn: 'yellow',
  debug: 'blue',
  error: 'red'
});

// outputs red text
console.log(@devtea2027/odit-ad-quisquam-tempore.error("this is an error"));

// outputs yellow text
console.log(@devtea2027/odit-ad-quisquam-tempore.warn("this is a warning"));

```

### Combining Colors

```javascript
var @devtea2027/odit-ad-quisquam-tempore = require('@devtea2027/odit-ad-quisquam-tempore');

@devtea2027/odit-ad-quisquam-tempore.setTheme({
  custom: ['red', 'underline']
});

console.log('test'.custom);
```

*Protip: There is a secret undocumented style in `@devtea2027/odit-ad-quisquam-tempore`. If you find the style you can summon him.*
