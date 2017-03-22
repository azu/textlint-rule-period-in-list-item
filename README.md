# textlint-rule-period-in-list-item [![textlint rule](https://img.shields.io/badge/textlint-fixable-green.svg?style=social)](https://textlint.github.io/) 

textlint rule that check with or without period in list item.

**Default** 

No period mark at end of the list item.
You can change the behavior by options.

**OK**:

```
- item
```

**NG**:

```
- item.
```


## Install

Install with [npm](https://www.npmjs.com/):

    npm install textlint-rule-period-in-list-item

## Usage

Via `.textlintrc`(Recommended)

```json
{
    "rules": {
        "period-in-list-item": true
    }
}
```

Via CLI

```
textlint --rule period-in-list-item README.md
```

## Options

```json
{
    // prefer to use period mark.
    // "" (default is no period)
    // You can select period mark like "." from "periodMarks".
    "periodMark": "",
    // Built-in recognized period mark list
    // if the period of the text is not `periodMark` and it is a string in the `periodMarks`,
    "periodMarks": [".", "。", "．"],
    // allow exception period mark list at end of the list item
    // Ignore this period mark
    "allowPeriodMarks": [],
    // Allow emoji at end of the list item
    "allowEmoji": false,
    // If not exist `periodMark` at end of the list item
    // Automatically, append `periodMark` when does textlint --fix
    "forceAppendPeriod": false
}
```

## Example

Use `.` as period mark at end of the list item.
Automatically, force append periodMark.

```json
{
    "rules": {
        "period-in-list-item": {
           "periodMark": ".",
           "forceAppendPeriod": true
        }
    }
}
```

**Before**

```
-item

<!-- Not exist period mark(".") at end of list item. -->
```

**After**

`textlint --fix` fixes this issue.

```
- item.
```

## Changelog

See [Releases page](https://github.com/azu/textlint-rule-period-in-list-item/releases).

## Running tests

Install devDependencies and Run `npm test`:

    npm i -d && npm test

## Contributing

Pull requests and stars are always welcome.

For bugs and feature requests, [please create an issue](https://github.com/azu/textlint-rule-period-in-list-item/issues).

1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request :D

## Author

- [github/azu](https://github.com/azu)
- [twitter/azu_re](https://twitter.com/azu_re)

## License

MIT © azu
