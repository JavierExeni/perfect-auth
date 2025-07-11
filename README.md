# PerfectAuth

VScode extensions

- Angular Language Service
- ESLint
- Prettier

Primeras instalaciones recomendadas cuando trabajar en equipos de desarrollo.

- angular-eslint | typescript-eslint | eslint
  https://eslint.org/

ng add angular-eslint

- prettier
  https://prettier.io/
  npm install --save-dev --save-exact prettier

Nuevo comando
"format": "prettier --write ."

Creas un .prettierrc.json

Y añade esta config por defecto:
{
"tabWidth": 2,
"useTabs": false,
"singleQuote": true,
"semi": true,
"bracketSpacing": true,
"arrowParens": "avoid",
"trailingComma": "es5",
"bracketSameLine": true,
"printWidth": 80,
"overrides": [
{
"files": "*.html",
"options": {
"parser": "angular"
}
}
]
}

Por el momento están trabajando de forma individual, pero la idea es que trabajaen juntas tanto eslint como prettier.

Para eso instalaremos los siguiente paquetes.

https://prettier.io/docs/related-projects#eslint-integrations

npm install prettier-eslint eslint-config-prettier eslint-plugin-prettier --save-dev

Then in your eslint.config.js import

const eslintPluginPrettierRecommended = require('eslint-plugin-prettier/recommended');

and add in your extends array

{
files: ['**/*.ts'],
extends: [
eslint.configs.recommended,
...tseslint.configs.recommended,
...tseslint.configs.stylistic,
...angular.configs.tsRecommended,
eslintPluginPrettierRecommended, <-- add this
],
...
