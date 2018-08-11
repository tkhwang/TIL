# eslint


## Disable `no-console` error

```
[eslint] Unexpected console statement. (no-console)
```

[javascript - Eslint: How to disable "unexpected console statement" in Node.js? - Stack Overflow](https://stackoverflow.com/questions/34215526/eslint-how-to-disable-unexpected-console-statement-in-node-js)

```
module.exports = {
  "extends": "airbnb-base",
  rules: {
    "no-console": 0
  }
};
```

## Enable eslint in VSCode project

[Setting up ESLint on VS Code with Airbnb JavaScript Style Guide](https://travishorn.com/setting-up-eslint-on-vs-code-with-airbnb-javascript-style-guide-6eb78a535ba6)

```bash
// Shell
npm init -y
npm i -D eslint eslint-config-airbnb-base eslint-plugin-import
Create .eslintrc.js: module.exports = { “extends”: “airbnb-base” };

// In VS Code, Ctrl + Shift + X
Search ESLint
Install ESLint
Restart VS Code
```
