# Monaco Editor Fix for Code Editor Addon

> This fix is provided to support the original author: [Leonardo R.](https://builtbybit.com/members/leonardo-r.244156/)

If you encounter any errors with the code editor addon, follow these steps:

---

## Step 1: Upload Files
Upload the contents of the `panelfiles` folder to your project.

---

## Step 2: Update Webpack Configuration (/var/www/pterodactyl/webpack.config.js)
Open the file:


Find this block:

```js
{
    test: /\.mjs$/,
    include: /node_modules/,
    type: 'javascript/auto',
},
```
Add this below:

```js
{
    test: /\.m?js$/,
    include: /node_modules\/@?monaco-editor/,
    type: 'javascript/auto',
    loader: 'esbuild-loader',
},
```

```
yarn add esbuild-loader
yarn add monaco-editor@0.43.0 @monaco-editor/react@4.4.6 monaco-editor-webpack-plugin
```

## Step 3: Build the panel:

https://pterodactyl.io/community/customization/panel.html
