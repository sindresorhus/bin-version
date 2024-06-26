# binary-version

> Get the version of a binary in [semver](https://github.com/npm/node-semver) format

## Install

```sh
npm install binary-version
```

## Usage

```console
$ curl --version
curl 7.30.0 (x86_64-apple-darwin13.0)
```

```js
import binaryVersion from 'binary-version';

console.log(await binaryVersion('curl'));
//=> '7.30.0'
```

```console
$ openssl version
OpenSSL 1.0.2d 9 Jul 2015
```

```js
import binaryVersion from 'binary-version';

console.log(await binaryVersion('openssl'));
//=> '1.0.2'
```

```console
$ openssl version
OpenSSL 1.0.2d 9 Jul 2015
```

```js
import binaryVersion from 'binary-version';

console.log(await binaryVersion('openssl', {args: ['version']}));
//=> '1.0.2'
```

## API

### binaryVersion(binary, options?)

Returns a `Promise<string>` with the version of the `binary`.

#### binary

Type: `string`

The name of or path to the binary to get the version from.

#### options

Type: `object`

##### args

Type: `string[]`

The arguments to pass to `binary` so that it will print its version.

If not specified, predefined arguments will be used for known binaries, or `['--version']` and `['version']` arguments will be tried.

## Related

- [binary-version-cli](https://github.com/sindresorhus/binary-version-cli) - CLI for this module
- [find-versions](https://github.com/sindresorhus/find-versions) - Find semver versions in a string
