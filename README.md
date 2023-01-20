# eslint-plugin-tailwindcss

![npm (scoped)](https://img.shields.io/npm/v/eslint-plugin-tailwindcss?style=for-the-badge) ![npm bundle size (scoped)](https://img.shields.io/npm/l/eslint-plugin-tailwindcss?style=for-the-badge)

![eslint-plugin-tailwindcss logo](.github/logo.png)

Rules enforcing best practices and consistency using [Tailwind CSS](https://tailwindcss.com/).

While you can use the official plugin [`prettier-plugin-tailwindcss`](https://www.npmjs.com/package/prettier-plugin-tailwindcss) for ordering your classnames...

**`eslint-plugin-tailwindcss` offers more than 5 other rules, that you can benefit from on top of `prettier-plugin-tailwindcss`. Sounds good ? Keep reading 👇**

## Supported Rules

Learn more about each supported rules by reading their documentation:

- [`classnames-order`](docs/rules/classnames-order.md): order classnames by target properties then by variants (`[size:][theme:][state:]`)
- [`enforces-negative-arbitrary-values`](docs/rules/enforces-negative-arbitrary-values.md): make sure to use negative arbitrary values classname without the negative classname e.g. `-top-[5px]` should become `top-[-5px]`
- [`enforces-shorthand`](docs/rules/enforces-shorthand.md): merge multiple classnames into shorthand if possible e.g. `mx-5 my-5` should become `m-5`
- [`migration-from-tailwind-2`](docs/rules/migration-from-tailwind-2.md) for easy upgrade from Tailwind CSS `v2` to `v3`.
  Warning: at the moment you should [temporary turn off the `no-custom-classname`](https://github.com/francoismassart/eslint-plugin-tailwindcss/issues/88) rule if you want to see the warning from `migration-from-tailwind-2`
- [`no-arbitrary-value`](docs/rules/no-arbitrary-value.md): forbid using arbitrary values in classnames (turned off by default)
- [`no-custom-classname`](docs/rules/no-custom-classname.md): only allow classnames from Tailwind CSS and the values from the `whitelist` option
- [`no-contradicting-classname`](docs/rules/no-contradicting-classname.md): e.g. avoid `p-2 p-3`, different Tailwind CSS classnames (`pt-2` & `pt-3`) but targeting the same property several times for the same variant.

Using ESLint extension for Visual Studio Code, you will get these messages
![detected-errors](.github/output.png)

You can can the same information on your favorite command line software as well.

## 🤝 Support `eslint-plugin-tailwindcss`

|                                                                                                                                                                                                                                       |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Premium Sponsors** <br /> Support us by becoming a sponsor. <br /> [Become a recurring sponsor](https://github.com/sponsors/francoismassart?frequency=recurring)                                                                    | <a href="https://daily.dev/" target="_blank"><img width="150px" src="https://raw.githubusercontent.com/francoismassart/eslint-plugin-tailwindcss/master/sponsors/daily.dev.jpg"></a>                                                                                                                                                                                                                                                                                                                                                           |
| **Current Sponsors** <br /> Any amount is appreciated.                                                                                                                                                                                | <a href="https://github.com/acewf" target="_blank"><img src="https://avatars.githubusercontent.com/u/4835572?s=60&amp;v=4" width="30" height="30" alt="@acewf"></a> <a href="https://github.com/charkour" target="_blank"><img src="https://avatars.githubusercontent.com/u/33156025?s=60&amp;v=4" width="30" height="30" alt="@charkour"></a> <a href="https://github.com/dailydotdev" target="_blank"><img class="avatar" src="https://avatars.githubusercontent.com/u/41463883?s=60&amp;v=4" width="30" height="30" alt="@dailydotdev"></a> |
| **Past sponsors** <br /> Even if this is just a one-time thing <br /> [Become a backer](https://github.com/sponsors/francoismassart?frequency=one-time)                                                                               | <a href="https://github.com/mongolyy" target="_blank"><img src="https://avatars.githubusercontent.com/u/10972787?s=60&amp;v=4" width="30" height="30" alt="@mongolyy"></a> <a href="https://github.com/t3dotgg" target="_blank"><img src="https://avatars.githubusercontent.com/u/6751787?s=60&amp;v=4" width="30" height="30" alt="@t3dotgg"></a>                                                                                                                                                                                             |
| **Contributors** <br /> This project can evolve thanks to all the people who contribute. <br /> You are welcome to [contribute](CONTRIBUTING.md) to this project by reporting issues, feature requests or even opening Pull Requests. | <a href="https://github.com/francoismassart/eslint-plugin-tailwindcss/graphs/contributors"><img src="https://contrib.rocks/image?repo=francoismassart/eslint-plugin-tailwindcss&width=300" /></a>                                                                                                                                                                                                                                                                                                                                              |

## We need you ❤️

If you enjoy my work you can:

- [Share the plugin on Twitter](https://twitter.com/hashtag/eslint-plugin-tailwindcss)
- Contribute to the project by:
  - Giving feedback
  - Creating an issue
  - Make a pull request
  - Write a feature request
- Give back and [sponsor its development](https://github.com/sponsors/francoismassart)

## Latest changelog

- feat: [Lint values in a object](https://github.com/francoismassart/eslint-plugin-tailwindcss/issues/135)
- feat: [Support for Object syntax in custom callees beside `classnames`](https://github.com/francoismassart/eslint-plugin-tailwindcss/pull/185)(by [dipsaus9](https://github.com/dipsaus9) 🙏)
- feat: [New option `skipClassAttribute`](https://github.com/francoismassart/eslint-plugin-tailwindcss/issues/154) you can turn on to only lint the `callees`
- FIX: support for Tailwind CSS version `3.2.3`

[View all releases on github](https://github.com/francoismassart/eslint-plugin-tailwindcss/releases)

## Installation

You'll first need to install [ESLint](http://eslint.org):

```
$ npm i -D eslint
```

Next, install the latest version of `eslint-plugin-tailwindcss` if you are using Tailwind CSS v3

```
$ npm i -D tailwindcss eslint-plugin-tailwindcss
```

> ### Still using Tailwind CSS v2?
>
> 👉 Install the latest version compatible with Tailwind CSS v2 via `npm i -D eslint-plugin-tailwindcss@tw2`
>
> Please note that new rules might not be available in the `tw2` distribution

Add `tailwindcss` to the plugins section of your `.eslintrc` configuration file. You can omit the `eslint-plugin-` prefix:

```json
{
  "plugins": ["tailwindcss"]
}
```

## Configuration

Use our preset to get reasonable defaults:

```
  "extends": [
    "plugin:tailwindcss/recommended"
  ]
```

If you do not use a preset you will need to specify individual rules and add extra configuration:

Configure the rules you want to use under the rules section.

> The following lines are matching the configuration saved in the `recommended` preset...

```json
{
  "rules": {
    "tailwindcss/classnames-order": "warn",
    "tailwindcss/enforces-negative-arbitrary-values": "warn",
    "tailwindcss/enforces-shorthand": "warn",
    "tailwindcss/migration-from-tailwind-2": "warn",
    "tailwindcss/no-arbitrary-value": "off",
    "tailwindcss/no-custom-classname": "warn",
    "tailwindcss/no-contradicting-classname": "error"
  }
}
```

Learn more about [Configuring Rules in ESLint](https://eslint.org/docs/user-guide/configuring/rules).

## Optional shared settings

Most rules shares the same settings, instead of duplicating some options...

You should also specify settings that will be shared across all the plugin rules.
[More about eslint shared settings](https://eslint.org/docs/user-guide/configuring#adding-shared-settings).

All these settings have nice default values that are explained in each rules' documentation. I'm listing them in the code below just to show them.

```json5
{
  settings: {
    tailwindcss: {
      // These are the default values but feel free to customize
      callees: ["classnames", "clsx", "ctl"],
      config: "tailwind.config.js",
      cssFiles: [
        "**/*.css",
        "!**/node_modules",
        "!**/.*",
        "!**/dist",
        "!**/build",
      ],
      cssFilesRefreshRate: 5_000,
      removeDuplicates: true,
      skipClassAttribute: false,
      whitelist: [],
      tags: [],
      classRegex: "^class(Name)?$", // can be modified to support custom attributes. E.g. "^tw$" for `twin.macro`
    },
  },
}
```

The plugin will look for each setting value in this order and stop looking as soon as it finds the settings:

1. In the rule option argument (rule level)
2. In the shared settings (plugin level)
3. Default value of the requested setting (plugin level)...

## Upcoming Rules

- `validate-modifiers`: I don't know if possible, but I'd like to make sure all the modifiers prefixes of a classname are valid e.g. `yolo:bg-red` should throw an error...

- `no-redundant-variant`: e.g. avoid `mx-5 sm:mx-5`, no need to redefine `mx` in `sm:` variant as it uses the same value (`5`)

- `only-valid-arbitrary-values`:
  - e.g. avoid `top-[42]`, only `0` value can be unitless.
  - e.g. avoid `text-[rgba(10%,20%,30,50%)]`, can't mix `%` and `0-255`.

## Alternatives

I wrote this plugin after searching for existing tools which perform the same task but didn't satisfied my needs:

- [prettier-plugin-tailwindcss](https://www.npmjs.com/package/prettier-plugin-tailwindcss), the official plugin, only takes care of ordering classnames, do not support array of classnames, do not support blade
- [eslint-plugin-tailwind](https://www.npmjs.com/package/eslint-plugin-tailwind), not bad but no support (yet) for variants sorting
- [Headwind](https://marketplace.visualstudio.com/items?itemName=heybourn.headwind), only works within Visual Studio Code
