# @tidusia/prettier-config

![Github actions](https://github.com/tidusia/prettier-config/actions/workflows/release.yml/badge.svg)
[![semantic-release](https://img.shields.io/badge/%20%20%F0%9F%93%A6%F0%9F%9A%80-semantic--release-e10079.svg)](https://github.com/semantic-release/semantic-release)

The way I found to share my favorite prettier config across projects

## Installation

```bash
npm i -D @tidusia/prettier-config prettier
```

Then create a `.prettierrc.js` file at the root of your project with the following content :

```js
module.exports = require("@tidusia/prettier-config");
```

## Usage

Add the following scripts to your package.json :

```json
{
  "scripts": {
    "prettier": "prettier --ignore-path .gitignore \"**/*.{js,jsx,ts,tsx,json,md}\"",
    "format": "npm run prettier -- --write",
    "format:check": "npm run prettier -- --list-different"
  }
}
```

The `format` command will format all files (not git-ignored) in your project that have the matching extension.

The `format:check` do not change files but check that all files are formatted properly. Something you can use in a pre-commit / CI for example.

## Optional : set up your IDE

For example, in Webstorm, open "Preferences" -> "Languages & Frameworks" -> "JavaScript" -> "Prettier" (you need the Prettier plugin).

Choose your preferred prettier package (from node_module VS globally installed for example).
Update the "Run for files:" glob pattern to match the pattern you specified in the `prettier` script in your `package.json` (from the section above).
