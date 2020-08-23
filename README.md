# eslint-prettier-project

This is a ready-to-code empty JS project with prettier and eslint supported.

## GUIDE:

1. Make sure you have `ESLint` and `Prettier` extensions installed and enabled in your VS Code.

2. Clone this repo to your local folder

    ```
    git clone https://github.com/LQF2020/eslint-prettier-project.git
    ```

3. Install relvant dev-dependency that are required to run eslint and prettier

    ```
    cd eslint-prettier-project && npm install
    ```

4. Modified `.eslintrc.json` and `.prettierrc` based on your need.

---

## USAGE

Eslint all your js files, run the following command:

```
npm run lint
```

Eslint all your js files with `auto-fix`, run the following command:

```
npm run lint:fix
```

> If any files that `NO` need to be eslinted, just put in `.eslintignore` file.

---

## Extension Tips

#### For `Prettier` Extension:

This extension will use prettier from your project's local dependencies (recommended). When the prettier.resolveGlobalModules is set to true the extension can also attempt to resolve global modules. Should prettier not be installed locally with your project's dependencies or globally on the machine, the version of prettier that is bundled with the extension will be used. By running `npm install prettier` in the workspace folder for a local install or `npm install -g prettier` for a global install.

#### For `Eslint` Extension:

The extension uses the ESLint library installed in the opened workspace folder. If the folder doesn't provide one the extension looks for a global install version. If you haven't installed ESLint either locally or globally do so by running `npm install eslint` in the workspace folder for a local install or `npm install -g eslint` for a global install.

---

## Dependency Explanation

A modules required by eslint to handle ES6 style syntax.

```
"babel-eslint": "^10.1.0"
```

A base dependency to use eslint in project.

```
"eslint": "^7.2.0"
```

A base dependency to use prettify in project.

```
"prettier": "^2.0.5"
```

It helps to embed prettier format-checking rules into eslint syntax-quality checking rules.

```
"eslint-config-prettier": "^6.11.0"
```

With this plugin, eslint is able to use prettier to format all js files When using `eslint --fix`,

```
"eslint-plugin-prettier": "^3.1.4"
```

We could use the following depedencies to config eslint to use `Airbnb` base standard. Airbnb also has react plugin supports. For more details, go to [Here](https://www.npmjs.com/package/eslint-config-airbnb).

```
"eslint-plugin-import": "^2.21.2"
"eslint-config-airbnb-base": "^14.2.0"
```

Similar purpose as above.

```
"eslint-plugin-node": "^11.1.0",
"eslint-config-node": "^4.1.0",
```

After running installing all packages,
make sure your eslint configuration file `.eslintrc.json` has the following:

```
{
    "extends": ["airbnb-base", "plugin:prettier/recommended"],
    "parserOptions": {
        "ecmaVersion": 2015
    },
    "parser": "babel-eslint",
    "rules": {
		\\ any rules that you might like ,for example:
        "no-unused-vars": "warn",
        "no-console": "off",
        "func-names": "off",
        "object-shorthand": "off"
    }
}
```
