# stylelint-color-format

A [Stylelint] plugin to convert HEX colors to either RGB or HSL formats.

## Installation

```sh
npm install --save-dev stylelint-color-format
```

## Configuration

In you [Stylelint Configuration], add the following to the plugins:

```json
{
  "plugins": ["stylelint-color-format"]
}
```

And then, in the rules:

```json
{
  "rules": {
    "color-format/format": {
      "format": "rgb"
    }
  }
}
```

## Usage

The rule itself works much like the default [`color-no-hex`] rule. It will report if a HEX color format (#333, #CA4FBD and even #FFFFFFAB) is found, it will error out since the format is not what we want.
If you pass the `--fix` option, however, the color format will be converted to either `rgb` or `hsl`, according
to your configuration

## Configuration

The `color-format/format` rule accepts an object with a single `format` key.

#### `rgb` | `rgba`

This will convert any HEX colors to RGB. If the HEX color has a transparency, the RGBA format will be used.

#### `hsl` | `hsla`

This will convert any HEX colors to HSL. If the HEX color has a transparency, the RGBA format will be used.

LICENSE - [MIT]

[stylelint]: https://github.com/stylelint/stylelint/
[style configuration]: https://github.com/stylelint/stylelint/blob/master/docs/user-guide/configuration.md
[`color-no-hex`]: https://github.com/stylelint/stylelint/blob/master/lib/rules/color-no-hex/README.md
[mit]: LICENSE.md