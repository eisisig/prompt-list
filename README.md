# prompt-list [![NPM version](https://img.shields.io/npm/v/prompt-list.svg?style=flat)](https://www.npmjs.com/package/prompt-list) [![NPM downloads](https://img.shields.io/npm/dm/prompt-list.svg?style=flat)](https://npmjs.org/package/prompt-list)

> List-style prompt. Can be used as a standalone prompt, or with a prompt system like [Enquirer](https://github.com/enquirer/enquirer).

![prompt-list example](https://raw.githubusercontent.com/enquirer/prompt-list/master/example.gif)

## Install

Install with [npm](https://www.npmjs.com/):

```sh
$ npm install --save prompt-list
```

## Example usage

```js
var List = require('prompt-list');
var list = new List({
  type: 'list',
  name: 'order',
  message: 'What would you like to order?',
  choices: [
    'Coke',
    'Diet Coke',
    'Cherry Coke',
    {
      name: 'Sprite',
      disabled: 'Temporarily unavailable'
    },
    'Water'
  ]
});

// promise
list.run()
  .then(function(answer) {
    console.log(answer);
  });

// or async
list.ask(function(answer) {
  console.log(answer);
});
```

## Enquirer usage

```js
var Enquirer = require('enquirer');
var enquirer = new Enquirer();

enquirer.register('list', require('prompt-list'));

var questions = [
  {
    type: 'list',
    name: 'order',
    message: 'What would you like to order?',
    choices: [
      'Coke',
      'Diet Coke',
      'Cherry Coke',
      {
        name: 'Sprite',
        disabled: 'Temporarily unavailable'
      },
      'Water'
    ]
  }
];

enquirer.ask(questions)
  .then(function(answers) {
    console.log(answers);
  })
  .catch(function(err) {
    console.log(err);
  });
```

## Attribution

Based on the `list` prompt in inquirer.

## About

### Related projects

* [enquirer-prompt](https://www.npmjs.com/package/enquirer-prompt): Base prompt module used for creating custom prompt types for Enquirer. | [homepage](https://github.com/jonschlinkert/enquirer-prompt "Base prompt module used for creating custom prompt types for Enquirer.")
* [enquirer-question](https://www.npmjs.com/package/enquirer-question): Question object, used by Enquirer and prompt plugins. | [homepage](https://github.com/enquirer/enquirer-question "Question object, used by Enquirer and prompt plugins.")
* [enquirer](https://www.npmjs.com/package/enquirer): Intuitive, plugin-based prompt system for node.js. Much faster and lighter alternative to Inquirer, with all… [more](https://github.com/enquirer/enquirer) | [homepage](https://github.com/enquirer/enquirer "Intuitive, plugin-based prompt system for node.js. Much faster and lighter alternative to Inquirer, with all the same prompt types and more, but without the bloat.")

### Contributing

Pull requests and stars are always welcome. For bugs and feature requests, [please create an issue](../../issues/new).

### Running tests

Install dev dependencies:

```sh
$ npm install -d && npm test
```

### Author

**Jon Schlinkert**

* [github/jonschlinkert](https://github.com/jonschlinkert)
* [twitter/jonschlinkert](http://twitter.com/jonschlinkert)

### License

Copyright © 2016, [Jon Schlinkert](https://github.com/jonschlinkert).
Released under the [MIT license](https://github.com/enquirer/prompt-list/blob/master/LICENSE).

***

_This file was generated by [verb-generate-readme](https://github.com/verbose/verb-generate-readme), v0.1.31, on September 21, 2016._