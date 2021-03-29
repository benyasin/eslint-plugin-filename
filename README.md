# eslint-plugin-filename

Adds an ESLint rule to enforce filename conventions for linted files. Allows different options for different file extensions. Supports custom regular expressions.

[![NPM Version][npm-image]][npm-url]
[![NPM Downloads][downloads-image]][downloads-url]
[![Build Status][travis-image]][travis-url]
[![Coverage Status][coverage-image]][coverage-url]
[![License: MIT][license-image]][license-url]


## Installation

```bash
$ npm install -D eslint-plugin-filename
```

The following built-in values are supported: `pascalcase`/`PascalCase`, `camelcase`/`camelCase`, `snakecase`/`snake_case`, `kebabcase`/`kebab-case`.
Multiple built-in values passed as array are also supported.

Add it to your `.eslintrc.js`:

```js
module.exports = {
  plugins: [
    'filename',
  ],
  rules: {
    'filename/match': [2, 'camelcase'],
  },
};
```

or

```js
module.exports = {
  plugins: [
    'filename',
  ],
  rules: {
    'filename/match': [2, ['camelcase','pascalcase']],
  },
};
```

## Plugin Options

You can also provide your own regex, if you are using your own regex, do not pass them as array.

```js
'filename/match': [2, /^([a-z]+-)*[a-z]+(?:\..*)?$/],
```

You can also specify different options for different file extensions. In this case the plugin will only check files with extensions you explicitly provided:

```js
'filename/match': [2, { '.js': 'camelCase', '.ts': /^([a-z]+-)*[a-z]+(?:\..*)?$/ }],
```

## License

MIT

[npm-image]: https://img.shields.io/npm/v/eslint-plugin-filename.svg?style=flat-square
[npm-url]: https://npmjs.org/package/eslint-plugin-filename
[downloads-image]: https://img.shields.io/npm/dm/eslint-plugin-filename.svg?style=flat-square
[downloads-url]: https://npmjs.org/package/eslint-plugin-filename
[travis-image]: https://img.shields.io/travis/dolsem/eslint-plugin-filename.svg?style=flat-square
[travis-url]: https://travis-ci.org/dolsem/eslint-plugin-filename
[coverage-image]: https://img.shields.io/coveralls/dolsem/eslint-plugin-filename.svg?style=flat-square
[coverage-url]: https://coveralls.io/github/dolsem/eslint-plugin-filename?branch=master
[license-image]: https://img.shields.io/badge/License-MIT-blue.svg?style=flat-square
[license-url]: https://opensource.org/licenses/MIT
