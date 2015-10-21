# generator-travis

[![NPM version][npm-image]][npm-url]
[![Build Status][travis-image]][travis-url]
[![Dependency Status][depstat-image]][depstat-url]

> Get and keep `.travis.yml` up-to-date effortlessly

This package is useful if you want to keep your [Travis-CI][travis] configuration up to date effortlessly. Works great with other generators too.

The configuration template includes the following NodeJS versions:

* stable (v4)
* v0.12
* 0.10.


## Install

```
  npm install -g yo generator-travis
```
## Usage

```
  yo travis
```

## NodeJS versions in the config

Every LTS-supported version is included.

Once a version version becomes
LTS-unsupported, it will be removed from the config template and this generator
will get a minor version update.

* NodeJS `v0.10` will be removed **October 1, 2016**.
* NodeJS `v0.12` will be removed **April 1, 2017**.
* NodeJS `v4.2.0` will be removed **April 1, 2018**.

[Read more][NodeJS/LTS] about NodeJS long-term support/LTS.

[NodeJS/LTS]: https://github.com/nodejs/LTS/

## Composability

> Composability is a way to combine smaller parts to make one large thing. Sort of [like Voltron®][voltron]  
> — [Yeoman docs](http://yeoman.io/authoring/composability.html)

Just plug in _travis_ into your generator and let it handle your `.travis.yml` template for you. Everybody wins.

### Install

```
  npm install -S generator-travis
```

#### Compose

```js
this.composeWith('travis', {}, {
  local: require.resolve('generator-travis/generators/app')
});
```

Add any extra fields you need to `options.config` to extend the default configuration.

```js
this.composeWith('travis', { options: {
  config: { after_script: ['npm run coveralls'] }
}}, {
  local: require.resolve('generator-travis/generators/app')
});
```

[voltron]: http://25.media.tumblr.com/tumblr_m1zllfCJV21r8gq9go11_250.gif

## License

MIT © [Vladimir Starkov](https://iamstarkov.com)

[npm-url]: https://npmjs.org/package/generator-travis
[npm-image]: https://img.shields.io/npm/v/generator-travis.svg?style=flat-square

[travis-url]: https://travis-ci.org/iamstarkov/generator-travis
[travis-image]: https://img.shields.io/travis/iamstarkov/generator-travis.svg?style=flat-square

[depstat-url]: https://david-dm.org/iamstarkov/generator-travis
[depstat-image]: https://david-dm.org/iamstarkov/generator-travis.svg?style=flat-square

[travis]: https://travis-ci.org/
