Deno clipboard library
=

[![Build Status](https://github.com/rsp/deno-clipboard/workflows/ci/badge.svg?branch=master&event=push)](https://github.com/rsp/deno-clipboard/actions)

Experimental. Work in progress.

Note: The clipboard on Windows always adds a trailing newline if there was none
which makes single line strings end with newline and this module removes the
trailing newline on Windows, but it mens that if it was there originally it will still
be removed - to preserve single-ine strings being single line, but maybe this is not the right
way to do it. The other option would be to preserve the trailing newline but also to get one
if it wasn't there. Currently I chose to remove it because newlines in the clipboard sometimes
are problemating. TODO: think about it.

Goals:

- use Web [Clipboard API](https://developer.mozilla.org/en-US/docs/Web/API/Clipboard)
- use readText and writeText (no read and write, see the spec)
- work on Linux, macOS, Windows
- don't bundle any binaries

It will spawn external processes so unfortunately
it will require the all-powerful `--allow-run` flag.

If Deno exposes a Clipboard API
(with new permissions like `--allow-copy` ale `--allow-paste`)
then hopefully this will be obsolete.

Usage
-

```ts
import { clipboard } from './mod.ts';

await clipboard.writeText('some text');

const text = await clipboard.readText();

text === 'some text';
```

Issues
-
For any bug reports or feature requests please
[post an issue on GitHub][issues-url].

Author
-
[**Rafał Pocztarski**](https://pocztarski.com/)
<br/>
[![Follow on GitHub][github-follow-img]][github-follow-url]
[![Follow on Twitter][twitter-follow-img]][twitter-follow-url]
<br/>
[![Follow on Stack Exchange][stackexchange-img]][stackoverflow-url]

License
-
MIT License (Expat). See [LICENSE.md](LICENSE.md) for details.

[github-url]: https://github.com/rsp/deno-clipboard
[readme-url]: https://github.com/rsp/deno-clipboard#readme
[issues-url]: https://github.com/rsp/deno-clipboard/issues
[license-url]: https://github.com/rsp/deno-clipboard/blob/master/LICENSE.md
[travis-url]: https://travis-ci.org/rsp/deno-clipboard
[travis-img]: https://travis-ci.org/rsp/deno-clipboard.svg?branch=master
[snyk-url]: https://snyk.io/test/github/rsp/deno-clipboard
[snyk-img]: https://snyk.io/test/github/rsp/deno-clipboard/badge.svg
[david-url]: https://david-dm.org/rsp/deno-clipboard
[david-img]: https://david-dm.org/rsp/deno-clipboard/status.svg
[install-img]: https://nodei.co/npm/ende.png?compact=true
[downloads-img]: https://img.shields.io/npm/dt/ende.svg
[license-img]: https://img.shields.io/npm/l/ende.svg
[stats-url]: http://npm-stat.com/charts.html?package=ende
[github-follow-url]: https://github.com/rsp
[github-follow-img]: https://img.shields.io/github/followers/rsp.svg?style=social&logo=github&label=Follow
[twitter-follow-url]: https://twitter.com/intent/follow?screen_name=pocztarski
[twitter-follow-img]: https://img.shields.io/twitter/follow/pocztarski.svg?style=social&logo=twitter&label=Follow
[stackoverflow-url]: https://stackoverflow.com/users/613198/rsp
[stackexchange-url]: https://stackexchange.com/users/303952/rsp
[stackexchange-img]: https://stackexchange.com/users/flair/303952.png
