# Neutrino Banner Middleware

`@neutrinojs/banner` is Neutrino middleware for injecting string content into source code files.

[![NPM version][npm-image]][npm-url]
[![NPM downloads][npm-downloads]][npm-url]
[![Join the Neutrino community on Spectrum][spectrum-image]][spectrum-url]

## Requirements

- Node.js v6.10+
- Yarn or npm client
- Neutrino v7

## Installation

`@neutrinojs/banner` can be installed via the Yarn or npm clients.

#### Yarn

```bash
❯ yarn add @neutrinojs/banner
```

#### npm

```bash
❯ npm install --save @neutrinojs/banner
```

## Usage

`@neutrinojs/banner` can be consumed from the Neutrino API, middleware, or presets. Require this package
and plug it into Neutrino:

```js
// Using function middleware format:
const banner = require('@neutrinojs/banner');

// Use with default options
neutrino.use(banner);

// Also accepts options for Webpack's BannerPlugin
// https://webpack.js.org/plugins/banner-plugin/

// Usage shows the default values of this middleware:
neutrino.use(banner, {
  banner: `require('source-map-support').install();`,
  raw: true,
  entryOnly: true
});
```

```js
// Using object or array middleware format:
const banner = require('@neutrinojs/banner');

// Use with default options
module.exports = {
  use: ['@neutrinojs/banner']
};

// Also accepts options for Webpack's BannerPlugin
// https://webpack.js.org/plugins/banner-plugin/

// Usage shows the default values of this middleware:
module.exports = {
  use: [
    ['@neutrinojs/banner', {
      banner: `require('source-map-support').install();`,
      raw: true,
      entryOnly: true
    }]
  ]
};
```

## Customization

`@neutrinojs/banner` creates some conventions to make overriding the configuration easier once you are ready to
make changes.

### Plugins

The following is a list of plugins and their identifiers which can be overridden:

| Name | Description | Environments and Commands |
| --- | --- | --- |
| `banner` | Injects string content into application source code. | all |

## Contributing

This middleware is part of the [neutrino-dev](https://github.com/mozilla-neutrino/neutrino-dev) repository, a monorepo
containing all resources for developing Neutrino and its core presets and middleware. Follow the
[contributing guide](https://neutrino.js.org/contributing) for details.

[npm-image]: https://img.shields.io/npm/v/@neutrinojs/banner.svg
[npm-downloads]: https://img.shields.io/npm/dt/@neutrinojs/banner.svg
[npm-url]: https://npmjs.org/package/@neutrinojs/banner
[spectrum-image]: https://withspectrum.github.io/badge/badge.svg
[spectrum-url]: https://spectrum.chat/neutrino
