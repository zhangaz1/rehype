# rehype

[![Build][build-badge]][build]
[![Coverage][coverage-badge]][coverage]
[![Downloads][downloads-badge]][downloads]
[![Size][size-badge]][size]
[![Sponsors][sponsors-badge]][collective]
[![Backers][backers-badge]][collective]
[![Chat][chat-badge]][chat]

[**unified**][unified] processor to parse and serialize HTML.
Powered by [plugins][].
Part of the [unified][] [collective][].

*   API by [**unified**][unified]
*   Parses HTML to the tree with [`rehype-parse`][parse]
*   [**hast**][hast] syntax tree
*   [Plugins][] transform the tree
*   Serializes the tree to HTML with [`rehype-stringify`][stringify]

Don’t need the parser?
Or the compiler?
[That’s OK][unified-use].

If you’re in a browser, trust the content, and value a smaller bundle size, use
[`rehype-dom`][rehype-dom] instead.

## Sponsors

<!--lint ignore no-html-->

<table>
  <tr valign="top">
    <td width="33.33%" align="center" colspan="2">
      <a href="https://www.gatsbyjs.org">Gatsby</a><br>🥇<br><br>
      <a href="https://www.gatsbyjs.org"><img src="https://avatars1.githubusercontent.com/u/12551863?s=900&v=4"></a>
    </td>
    <td width="33.33%" align="center" colspan="2">
      <a href="https://vercel.com">Vercel</a><br>🥇<br><br>
      <!--OC has a sharper image-->
      <a href="https://vercel.com"><img src="https://images.opencollective.com/vercel/d8a5bee/logo/512.png"></a>
    </td>
    <td width="33.33%" align="center" colspan="2">
      <a href="https://www.netlify.com">Netlify</a><br><br><br>
      <!--OC has a sharper image-->
      <a href="https://www.netlify.com"><img src="https://images.opencollective.com/netlify/4087de2/logo/512.png"></a>
    </td>
  </tr>
  <tr valign="top">
    <td width="16.67%" align="center">
      <a href="https://www.holloway.com">Holloway</a><br><br><br>
      <a href="https://www.holloway.com"><img src="https://avatars1.githubusercontent.com/u/35904294?s=300&v=4"></a>
    </td>
    <td width="16.67%" align="center">
      <a href="https://themeisle.com">ThemeIsle</a><br>🥉<br><br>
      <a href="https://themeisle.com"><img src="https://twitter-avatar.now.sh/themeisle"></a>
    </td>
    <td width="16.67%" align="center">
      <a href="https://boostio.co">BoostIO</a><br>🥉<br><br>
      <a href="https://boostio.co"><img src="https://avatars1.githubusercontent.com/u/13612118?s=300&v=4"></a>
    </td>
    <td width="16.67%" align="center">
      <a href="https://expo.io">Expo</a><br>🥉<br><br>
      <a href="https://expo.io"><img src="https://avatars1.githubusercontent.com/u/12504344?s=300&v=4"></a>
    </td>
    <td width="50%" align="center" colspan="2">
      <br><br><br><br>
      <a href="https://opencollective.com/unified"><strong>You?</strong></a>
    </td>
  </tr>
</table>

## Install

[npm][]:

```sh
npm install rehype
```

## Use

```js
var rehype = require('rehype')
var report = require('vfile-reporter')

rehype().process('<title>Hi</title><h2>Hello world!', function(err, file) {
  console.log(report(err || file))
  console.log(String(file))
})
```

Yields:

```txt
no issues found
<html><head><title>Hi</title></head><body><h2>Hello world!</h2></body></html>
```

Configuration for [`rehype-parse`][parse] and [`rehype-stringify`][stringify]
can be set with `.data('settings', {/*...*/})`.

## Security

As **rehype** works on HTML, and improper use of HTML can open you up to a
[cross-site scripting (XSS)][xss] attack, use of rehype can also be unsafe.
Use [`rehype-sanitize`][sanitize] to make the tree safe.

## Contribute

See [`contributing.md`][contributing] in [`rehypejs/.github`][health] for ways
to get started.
See [`support.md`][support] for ways to get help.
Ideas for new plugins and tools can be posted in [`rehypejs/ideas`][ideas].

A curated list of awesome rehype resources can be found in [**awesome
rehype**][awesome].

This project has a [code of conduct][coc].
By interacting with this repository, organization, or community you agree to
abide by its terms.

## License

[MIT][license] © [Titus Wormer][author]

<!-- Definitions -->

[build-badge]: https://img.shields.io/travis/rehypejs/rehype.svg

[build]: https://travis-ci.org/rehypejs/rehype

[coverage-badge]: https://img.shields.io/codecov/c/github/rehypejs/rehype.svg

[coverage]: https://codecov.io/github/rehypejs/rehype

[downloads-badge]: https://img.shields.io/npm/dm/rehype.svg

[downloads]: https://www.npmjs.com/package/rehype

[size-badge]: https://img.shields.io/bundlephobia/minzip/rehype.svg

[size]: https://bundlephobia.com/result?p=rehype

[sponsors-badge]: https://opencollective.com/unified/sponsors/badge.svg

[backers-badge]: https://opencollective.com/unified/backers/badge.svg

[collective]: https://opencollective.com/unified

[chat-badge]: https://img.shields.io/badge/chat-spectrum-7b16ff.svg

[chat]: https://spectrum.chat/unified/rehype

[health]: https://github.com/rehypejs/.github

[contributing]: https://github.com/rehypejs/.github/blob/HEAD/contributing.md

[support]: https://github.com/rehypejs/.github/blob/HEAD/support.md

[coc]: https://github.com/rehypejs/.github/blob/HEAD/code-of-conduct.md

[ideas]: https://github.com/rehypejs/ideas

[awesome]: https://github.com/rehypejs/awesome-rehype

[license]: https://github.com/rehypejs/rehype/blob/main/license

[author]: https://wooorm.com

[npm]: https://docs.npmjs.com/cli/install

[unified]: https://github.com/unifiedjs/unified

[hast]: https://github.com/syntax-tree/hast

[parse]: https://github.com/rehypejs/rehype/blob/main/packages/rehype-parse

[stringify]: https://github.com/rehypejs/rehype/blob/main/packages/rehype-stringify

[rehype-dom]: https://github.com/rehypejs/rehype-dom/tree/HEAD/packages/rehype-dom

[plugins]: https://github.com/rehypejs/rehype/blob/main/doc/plugins.md

[unified-use]: https://github.com/unifiedjs/unified#use

[sanitize]: https://github.com/rehypejs/rehype-sanitize

[xss]: https://en.wikipedia.org/wiki/Cross-site_scripting
