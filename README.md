fixclosure [![Build Status](https://secure.travis-ci.org/teppeis/fixclosure.png?branch=master)](https://travis-ci.org/teppeis/fixclosure)
====
fixclosure is JavaScirpt linter/fixer based on Esprima for Google Closure Library.
now alpha version...

## Install

```bash
$ npm install -g fixclosure
```

## Usage

```bash
# Just lint
$ fixclosure foo.js

# Lint & Fix in place
$ fixclosure -f foo.js

# Specify roots of target packages in addition to "goog"
$ fixclosure --roots foo,bar foo.js

# Specify methods exported as a package itself like "goog.dispose"
$ fixclosure --packageMethods foo.foo1,bar.bar1 foo.js

# Replace method name that doesn't belong to the prefix package like "goog.disposeAll:goog.dispose"
$ fixclosure --replaceMap foo.foobar:foo.foo foo.js
```


## Changelog

* 0.1.3 (2012/12/08)
  * Append package methods of Closure Library.
  * Change version option from -V to -v.
  * Change exit code of invalid argument to 1.
  * Fix for private properties.
* 0.1.2 (2012/11/28)
  * Supports const property correctly.
  * Supports a method starting with "$".
  * Ignore goog.global.
  * Don't provide @typedef type resources.
  * Fix #5 don't provide a private class.
  * Fix #6 Don't require a private method defined in the same file.
  * Add some package methods.
* 0.1.1 (2012/11/25)
  * Scope check (by piglovesyou)
  * Root package filter works for toProvide list.
* 0.1.0 Add some options
  * Changes "fix in place" option to "-f" from "-i"
  * Implements root package filter (default: "goog")
  * Adds options --roots, --packageMethods and --replaceMap
* 0.0.2 Bugfix
* 0.0.1 Initial release

### License

MIT License: teppeis@gmail.com
