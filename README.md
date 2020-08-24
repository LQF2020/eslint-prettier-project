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

Make sure you have `npx` npm package runner( npx is pre-bundled with npm 5.2.0 ).
If not, please install globally:

```
npm install -g npx
```

Eslint all your js files, run the following command:

```
npm run lint
```

Eslint all your js files with `auto-fix`, which also let `prettier` implement code formatting, run the following command:

```
npm run lint:fix
```

> If any files that `NO` need to be eslinted, just put in `.eslintignore` file.
> If any files that `NO` need to be prettified, just put in `.prettierignore` file.

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
babel-eslint
```

A base dependency to use eslint in project.

```
eslint
```

A base dependency to use prettify in project.

```
prettier
```

It helps to embed prettier format-checking rules into eslint syntax-quality checking rules.

```
eslint-config-prettier
```

With this plugin, eslint is able to use prettier to format all js files When using `eslint --fix`,

```
eslint-plugin-prettier
```

We could use the following depedencies to config eslint to use `Airbnb` base standard. Airbnb also has `Reactjs` plugin supports. For more details, go to [Here](https://www.npmjs.com/package/eslint-config-airbnb).

```
eslint-plugin-import
eslint-config-airbnb-base
```

Similar purpose as above.

```
eslint-plugin-node
eslint-config-node
```

After installing all packages,
make sure your eslint configuration file `.eslintrc.json` has the following:

```
{
    "extends": ["airbnb-base", "plugin:prettier/recommended"],
    "parserOptions": {
        "ecmaVersion": 2015
    },
    "parser": "babel-eslint",
    "rules": {
  \\ create any rules that you might like ,for example:
        "no-unused-vars": "warn",
        "no-console": "off",
        "func-names": "off",
        "object-shorthand": "off"
    }
}
```
