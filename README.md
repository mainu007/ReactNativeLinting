# Linting for React Native

### First you remove these files(eslintrc and prettierrc) in root dir

### Install linting dependencies

```
yarn add --dev eslint prettier eslint-config-prettier
```

### Setup eslint

```
npx eslint --init
```

```bash
# question 1:
? How would you like to use ESLint? …
  To check syntax only
  To check syntax and find problems
❯ To check syntax, find problems, and enforce code style
# question 2:
? What type of modules does your project use? …
❯ JavaScript modules (import/export)
  CommonJS (require/exports)
  None of these
# question 3:
? Which framework does your project use? …
❯ React
  Vue.js
  None of these
# question 4 (select "No", because we won't add TypeScript support for this project):
? Does your project use TypeScript? › No / Yes
# question 5:
? Where does your code run? …
  Browser
✔ Node
# question 6:
? How would you like to define a style for your project? …
❯ Use a popular style guide
  Answer questions about your style
  Inspect your JavaScript file(s)
# question 7 (we'll rely on Airbnb's JavaScript style guide here):
? Which style guide do you want to follow? …
❯ Airbnb: https://github.com/airbnb/javascript
  Standard: https://github.com/standard/standard
  Google: https://github.com/google/eslint-config-google
# question 8:
? What format do you want your config file to be in? …
  JavaScript
  YAML
❯ JSON
# the final prompt here is where eslint will ask you if you want to install all the necessary dependencies. Select "Yes" and hit enter:
Checking peerDependencies of eslint-config-airbnb@latest
The config that you have selected requires the following dependencies:
eslint-plugin-react@^7.28.0 eslint-config-airbnb@latest eslint@^7.32.0 || ^8.2.0 eslint-plugin-import@^2.25.3 eslint-plugin-jsx-a11y@^6.5.1 eslint-plugin-react-hooks@^4.3.0
✔ Would you like to install them now? · No / Yes
✔ Which package manager do you want to use? · yarn
```

### Add prettier to the end of extends section

#### .eslintrc.json

```
"extends": [
  ...,
  "prettier"
  ],
```

### Add linter and prettier script to the script section in package.json file

#### package.json

```
"scripts": {
  ...,
  "linter": "eslint 'src/**/*.{js,jsx}'",
  "prettier": "prettier --write 'src/**/*.{js,jsx}'"
},
```

### Initialized Git

```
git init
```

### Install and setup Husky

```
yarn add --dev husky
```

### Enable Husky Git hooks

```
npx husky install
```

### To add a Husky command

```
npx husky add .husky/pre-commit "yarn linter"
npx husky add .husky/pre-commit "yarn prettier"
```
