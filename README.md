# ember-tb-test-helpers

This README outlines the details of collaborating on this Ember addon.
## Usage

First, install the addon:

    $ ember install ember-tb-test-helpers

Then, import the helpers you need:

```js
// tests/helpers/start-app.js

import './ember-tb-test-helpers/test-helpers';
// ...
```

```js
// tests/acceptance/your-test.js
import { clickOn, findRole } from 'ember-tb-test-helpers';

test('it works', assert => {
  clickOn('Foo!');

  andThen(() => {
    assert.notInclude(findRole('foo').text(), 'bar', 'foo is not bar');
  });
});
```

To use the matchers, import them in your test helper:

```js
// tests/test-helper.js
import 'ember-tb-test-helpers/extend-qunit';
```

## Helpers

* `clickOn(text)` - Clicks on elements containing the text
* `clickRole(role)` - Clicks on elements with a matching `[data-role]`
* `findRole(role)` - Finds (with assert) an element with matching `[data-role]`
* `fillInField(name, value)` - Fills in a field with a `[name]` with the given
  value
* [`within(scope, block)`][within] - Scopes subsequent calls to test helpers by
  the provided selector.

[within]: tests/acceptance/app-uses-helpers-test.js

## QUnit Matchers

* `assert.include(needle, haystack)` - Asserts that the `needle` string is
  included in the `haystack` string
* `assert.notInclude(needle, haystack)` - Asserts that the `needle` string is
  included in the `haystack` string
* `assert.textEqual(expected, actual)` - Asserts that the `expected` string or
  node's text equals the `actual` string
* `assert.hasClass(expected, actual)` - Asserts that the `expected` node or
  selector has the `actual` class

## Installation

* `git clone` this repository
* `npm install`
* `bower install`

## Running

* `ember server`
* Visit your app at http://localhost:4200.

## Running Tests

* `ember test`
* `ember test --server`

## Building

* `ember build`

For more information on using ember-cli, visit [http://www.ember-cli.com/](http://www.ember-cli.com/).

## Contributing

See the [CONTRIBUTING] document.
Thank you, [contributors]!

  [CONTRIBUTING]: CONTRIBUTING.md
  [contributors]: https://github.com/thoughtbot/ember-tb-test-helpers/graphs/contributors

## License

ember-tb-test-helpers is Copyright (c) 2015 thoughtbot, inc.
It is free software, and may be redistributed
under the terms specified in the [LICENSE] file.

  [LICENSE]: /LICENSE.md

## About

ember-tb-test-helpers is maintained by [Sean Doyle][seanpdoyle].

![thoughtbot](https://thoughtbot.com/logo.png)

  [seanpdoyle]: https://github.com/seanpdoyle

ember-tb-test-helpers is maintained and funded by thoughtbot, inc.
The names and logos for thoughtbot are trademarks of thoughtbot, inc.

We love open source software!
See [our other projects][community]
or [hire us][hire] to help build your product.

  [community]: https://thoughtbot.com/community?utm_source=github
  [hire]: https://thoughtbot.com/hire-us?utm_source=github
