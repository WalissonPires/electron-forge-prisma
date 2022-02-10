# electron-forge-prisma

Prisma configuration example project with Electron-Forge using the Webpack+Typescript template.

# How use

- ```npm install```

- ```npm start```

# The problem

Prism has packaging problem. When using prism with webpack the following error happens:

```
A JavaScript error occurred in the main process
Uncaught Exception:
Error: Cannot find module '_http_common'
```

To fix it I added to your webpack configuration:

```javascript
// @file: webpack.main.config.js
module.exports = {
  /* more config */
  externals: {
    _http_common: '_http_common'
  }
};
```