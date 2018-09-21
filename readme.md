# import-modules-auto [![Build Status](https://travis-ci.org/sindresorhus/import-modules-auto.svg?branch=master)](https://travis-ci.org/sindresorhus/import-modules-auto)

Fork from [https://github.com/sindresorhus/import-modules](https://github.com/sindresorhus/import-modules)

Add when import Object-Module, merge Object without key-word.

> Import all modules in a directory smart

*This module is intentionally simple. Not interested in more features.*


## Install

```
$ npm install --save import-modules-auto
```


## Usage

```
.
└── dir
    ├── foo-bar.js  //function
    └── baz-faz.js  //object {test: 'value'}
```

```js
const importModules = require('import-modules-auto');
const modules = importModules('dir');

console.log(modules);
//=> {fooBar: [Function], bazFaz: [Function]}
```
```js
const importModules = require('import-modules-auto');
const modules = importModules('dir',{hasKey: false});

console.log(modules);
//=> {fooBar: [Function], test: 'value'}
```

## API

### importModules([directory], [options])

#### directory

Type: `string`<br>
Default: `__dirname`

Directory to import modules from. Unless you've modified [`require.extensions`](https://nodejs.org/api/globals.html#globals_require_extensions), that means any `.js`, `.json`, `.node` files, in that order. Does not recurse. Ignores the caller file and files starting with `.` or `_`.

#### options

Type: `Object`

##### camelize

Type: `boolean`<br>
Default: `true`

Convert dash-style names (`foo-bar`) to camel-case (`fooBar`).
##### haskey

Type: `boolean`<br>
Default: `true`

Can set module without key words, merge object.

## Related

- [import-from](https://github.com/sindresorhus/import-from) - Import a module from a given path
- [import-cwd](https://github.com/sindresorhus/import-cwd) - Import a module from the current working directory
- [import-lazy](https://github.com/sindresorhus/import-lazy) - Import a module lazily


## License

MIT © [webkong](https://blog.webkong.cn)
