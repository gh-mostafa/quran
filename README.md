# INIT

## 1 init

yarn create next-app . --typescript

## 2 add sass

npm install --save-dev sass

## 3 yarn lint

yarn lint ( !new version use lint so do'nt need to add it )

## 4.1 eslint-config-prettier

yarn add --dev eslint-config-prettier

### 4.2 add prettier to eslint config

>> .eslintrc.json
   "extends": ["next/core-web-vitals", "prettier"]

## 5 Path aliases and baseUrl

>> tsconfig.json
    "baseUrl": ".",
    "paths": {
      "@/pages/*": ["pages/*"],
      "@/styles/*": ["styles/*"],
      "@/components/*": ["components/*"]
    }

## 6 install husky

npm install husky -D
npm set-script prepare "husky install"
npm run prepare
npx husky add .husky/pre-commit "npm test" ( "#npm test" )

## 7.1 install lint-staged

npm install lint-staged -D

## 7.2 
>> root : .lintstagedrc.js
const path = require('path');

const buildEslintCommand = (filenames) =>
  `next lint --fix --file ${filenames
    .map((f) => path.relative(process.cwd(), f))
    .join(' --file ')}`;

module.exports = {
  '*.{js,jsx,ts,tsx}': [buildEslintCommand],
};
*/

## 7.3

>> pre-commit :
npx lint-staged

## 8 .prettierrc - config prettier

>> .prettierrc
{
  "singleQuote": true,
  "jsxSingleQuote": true,
  "trailingComma": "all"
}

# ADD MATERIAL UI

## 1 init

yarn add @mui/material
yarn add @fontsource/roboto
yarn add @mui/icons-material

yarn add @emotion/react @emotion/styled @emotion/server @emotion/cache

## 2 add some files

https://github.com/mui/material-ui/tree/master/examples/nextjs-with-typescript

## 3 RTL

https://mui.com/material-ui/guides/right-to-left/