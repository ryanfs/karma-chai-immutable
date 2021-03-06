karma-chai-immutable
==========

[![npm](https://img.shields.io/npm/dm/karma-chai-immutable.svg?maxAge=2592000)](https://www.npmjs.com/package/karma-chai-immutable)

Makes the [chai-immutable](https://github.com/astorije/chai-immutable) adapter for [Chai](http://chaijs.com) and [Immutable](https://facebook.github.io/immutable-js/) available in [Karma](http://karma-runner.github.io)

Installation
------------

```sh
$ npm install karma-chai-immutable --save-dev
```

Add `chai-immutable` to the `frameworks` key in your Karma configuration:

```js
module.exports = function(config) {
  'use strict';
  config.set({
    frameworks: ['mocha', 'chai-immutable'],
    #...
  });
}
```


Usage
-----

Chai matchers for Immutable are available in tests:

```js
describe('chai-immutable', function () {

  it('can compare objects', function () {
    var a = Immutable.Map({key: 'value'}),
        b = a.merge({key: 'value'}),
        c = a.merge({key: 'other value'});

    a.should.equal(b);
    a.should.not.equal(c);
  });

  it('can check if an Immutable is empty', function () {
    Immutable.List().should.be.empty;
  });
});
```

See [chai-immutable](https://github.com/astorije/chai-immutable) for full documentation.

Thanks
------

Cheers to [chai-immutable](https://github.com/astorije/chai-immutable) and [karma](https://github.com/karma-runner/karma)!
