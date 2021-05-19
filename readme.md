# @tidusia/prettier-config

The way I found to share my favorite prettier config across projects

## Installation

```bash
npm i -D @tidusia/prettier-config prettier
```

Then create a `.prettierrc.js` file at the root of your project with the following content :

```js
module.exports = require("@tidusia/prettier-config")
```

## Usage 

Add the following scripts to your package.json :

```json
{
  "scripts": {
    "prettier": "prettier --ignore-path .gitignore \"**/*.{js,jsx,ts,tsx,json,md}\"",
    "prettier:write": "npm run prettier -- --write",
    "prettier:check": "npm run prettier -- --list-different"
  }
}
```

The `prettier:write` command will format all files (not git-ignored) in your project that have the matching extension.

The `prettier:check` do not change files but check that all files are formatted properly. Something you can use in a pre-commit / CI for example.
